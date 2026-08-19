---
name: Pull a traffic report for a date range
description: >-
  Read visit and page metrics out of Matomo for one site and one period, with
  segmentation and pagination handled correctly.
api: openapi/matomo-visits-summary-openapi.json
operations:
  - VisitsSummary.get
  - VisitsSummary.getVisits
  - VisitsSummary.getUniqueVisitors
  - VisitsSummary.getActions
  - Actions.getPageUrls
  - Actions.getEntryPageUrls
  - Actions.getExitPageUrls
  - Referrers.getAll
  - API.getProcessedReport
  - API.getBulkRequest
---

# Pull a traffic report for a date range

## The coordinate system

Matomo does not have report resources you GET by id. Every read is addressed by a
four-part coordinate you pass as query parameters:

| Parameter | Meaning |
|---|---|
| `idSite` | Which site. Required on almost everything. |
| `period` | `day`, `week`, `month`, `year` or `range`. |
| `date` | `YYYY-MM-DD`, a magic keyword (`today`, `yesterday`, `lastWeek`, `lastMonth`, `lastYear`), or a range (`YYYY-MM-DD,YYYY-MM-DD`, `last7`, `previous30`). |
| `segment` | Optional filter expression. |

`period=range` with `date=2026-01-01,2026-01-31` is how you ask for an arbitrary window.

## Steps

1. **Get the overview.**
   Call `VisitsSummary.get` with `idSite`, `period`, `date`, `format=json`. One call
   returns visits, unique visitors, actions, bounces and visit duration together. Prefer
   this over calling `VisitsSummary.getVisits`, `VisitsSummary.getUniqueVisitors` and
   `VisitsSummary.getActions` separately — those exist for single-metric use and cost
   you three round trips for the same data.

2. **Get the page breakdown.**
   Call `Actions.getPageUrls` with the same coordinate. This returns a hierarchical
   table. Add `flat=1` to get a flat list of full URLs instead of a folder tree, or pass
   `idSubtable` to drill into one branch. `Actions.getEntryPageUrls` and
   `Actions.getExitPageUrls` give the landing and exit views.

3. **Get where the traffic came from.**
   Call `Referrers.getAll` for a single combined referrer table, or
   `Referrers.getReferrerType` for the channel-level rollup.

4. **Paginate.**
   Use `filter_limit` and `filter_offset`. The default limit is small; `filter_limit=-1`
   returns everything, which you should only do on reports you know are bounded. Sort
   with `filter_sort_column` and `filter_sort_order`. Filter rows with `filter_pattern`
   against `filter_column`.

5. **Segment, if needed.**
   Pass `segment=` with an expression such as `deviceType==smartphone` or
   `countryCode==de;visitCount>1`. `;` is AND, `,` is OR. Validate your dimension names
   against `API.getSegmentsMetadata` first — see the discovery skill.

6. **Batch when you need several reports at once.**
   `API.getBulkRequest` takes URL-encoded sub-requests in `urls[]` and returns all
   results in one response. Use it instead of hammering the instance — Matomo Cloud
   limits non-tracking requests to 2,000 per 10 minutes or 350 per minute per IP.

7. **When you want the report WITH its metadata**, call `API.getProcessedReport`
   instead of the module method directly. It returns the rows plus the column names,
   metric documentation and formatting the report catalog describes — which is what you
   want if a human or a model has to read the output.

## Failure modes

- `format` defaults to `xml`. If you get XML back, you forgot `format=json`.
- Live and Transitions endpoints have their own, tighter rate limits (200/min and
  500/5min per IP) and a per-account cap of 8 simultaneous raw-data queries.
- A `429` carries no `Retry-After` and no `RateLimit-*` headers. Back off exponentially;
  there is no budget to read.
