---
name: Create a saved segment and report against it
description: >-
  Define a reusable visitor segment in Matomo, then apply it to any report. Covers the
  write path, which is the part with no idempotency protection.
api: openapi/matomo-segment-editor-openapi.json
operations:
  - API.getSegmentsMetadata
  - API.getSuggestedValuesForSegment
  - SegmentEditor.isUserCanAddNewSegment
  - SegmentEditor.getAll
  - SegmentEditor.add
  - SegmentEditor.get
  - SegmentEditor.update
  - SegmentEditor.delete
  - VisitsSummary.get
---

# Create a saved segment and report against it

A segment is a filter definition. Once saved it has an `idSegment`, but the thing you
actually apply to reports is the segment DEFINITION string, passed as `segment=` on any
Reporting API call. 193 of Matomo's 556 documented operations accept it.

## Before writing

1. **Check permission.** Call `SegmentEditor.isUserCanAddNewSegment` with `idSite`. A
   token inherits its user's role; a view-only user cannot create segments.

2. **Check it does not already exist.** Call `SegmentEditor.getAll` with `idSite` and
   compare definitions. **This matters more here than it looks**: Matomo publishes no
   idempotency key and no request-deduplication contract, so calling
   `SegmentEditor.add` twice creates two segments. There is nothing on the server to
   stop you. A read-before-write is the only protection available.

3. **Build a valid definition.** Call `API.getSegmentsMetadata` with `idSite` for the
   dimensions this instance supports, and `API.getSuggestedValuesForSegment` for real
   values of a given dimension. Do not guess dimension names — an invalid one comes
   back as a `400` with a plain message, not a structured field error.

## Steps

1. **Create it.**
   `SegmentEditor.add` with `name`, `definition` (URL-encoded, e.g.
   `deviceType==smartphone;countryCode==de`), `idSite`, and optionally
   `autoArchive` and `enabledAllUsers`. Send it as a **POST** with the token in the
   body. Capture the returned `idSegment`.

2. **Verify.**
   `SegmentEditor.get` with `idSegment`. Confirm the definition round-tripped — encoding
   mistakes in the definition string are the usual cause of a segment that saves fine
   and then matches nothing.

3. **Apply it.**
   Call any report with `segment=<definition>`, for example `VisitsSummary.get` with
   `idSite`, `period`, `date`, `segment`, `format=json`. You pass the definition, not
   the id.

4. **Amend or remove.**
   `SegmentEditor.update` with `idSegment` to change it; `SegmentEditor.delete` to
   remove it. Both are unprotected writes — confirm the target with
   `SegmentEditor.get` first.

## Cost warning

A segment with `autoArchive=1` makes Matomo pre-process archives for it on every
period, which is real server work on the customer's own infrastructure. On a large
instance, creating many auto-archived segments is an expensive act. Leave it off
unless the segment will be read repeatedly.

## Agent surface

Matomo's MCP server exposes `matomo_segment_list` and `matomo_segment_get` for the read
path, but **no** dedicated tool for creating or updating a segment — writes are only
reachable through the raw-API executors (`matomo_api_call_create` /
`matomo_api_call_update`), which an administrator must deliberately enable. See
`mcp/matomo-tool-crosswalk.yml`.
