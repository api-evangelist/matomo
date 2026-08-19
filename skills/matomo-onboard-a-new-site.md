---
name: Onboard a new site and get its tracking code
description: >-
  Register a website in Matomo, retrieve the JavaScript tracking snippet, set up a goal,
  and confirm tracking is live — the full provisioning path an integrator automates.
api: openapi/matomo-sites-manager-openapi.json
operations:
  - SitesManager.getSitesIdFromSiteUrl
  - SitesManager.addSite
  - SitesManager.getSiteFromId
  - SitesManager.updateSite
  - SitesManager.getJavascriptTag
  - SitesManager.getImageTrackingCode
  - Goals.addGoal
  - Goals.getGoals
  - UsersManager.setUserAccess
  - Live.getCounters
  - VisitsSummary.getVisits
---

# Onboard a new site and get its tracking code

This is the write-heavy path, and Matomo gives you no safety net on it: there is no
idempotency key, so every one of these calls executed twice does the thing twice.
Check before you create.

## Steps

1. **Check the site does not already exist.**
   `SitesManager.getSitesIdFromSiteUrl` with `url`. If it returns an id, stop and use it.
   This read is the only duplicate protection available.

2. **Create the site.**
   `SitesManager.addSite` with `siteName` and `urls`. Useful optional parameters:
   `ecommerce=1`, `siteSearch=1`, `timezone`, `currency`, `excludedIps`,
   `excludedQueryParameters`, `type`. Send it as a **POST** with `token_auth` in the
   body. Capture the returned `idSite`.

   Requires admin or superuser access. A view-only token gets `403 — Not authorised.`

3. **Verify.**
   `SitesManager.getSiteFromId` with `idSite`. Confirm the URL list, timezone and
   currency came back as intended — timezone in particular silently defaults if you
   passed something Matomo does not recognise. `SitesManager.getTimezonesList` and
   `SitesManager.getCurrencyList` give the accepted values.

4. **Get the tracking code.**
   `SitesManager.getJavascriptTag` with `idSite` returns the ready-to-paste `_paq`
   snippet pointed at this instance. For environments without JavaScript — email, AMP,
   RSS — use `SitesManager.getImageTrackingCode` instead, which returns a 1×1 pixel URL.

5. **Define what success means.**
   `Goals.addGoal` with `idSite`, `name`, `matchAttribute` (`url`, `title`, `event`,
   `file`, `external_website`, `manually`), `pattern`, `patternType`
   (`contains`, `exact`, `regex`), and optionally `revenue`, `allowMultipleConversions`.
   Confirm with `Goals.getGoals`.

6. **Grant access.**
   `UsersManager.setUserAccess` with `userLogin`, `access` (`noaccess`, `view`, `write`,
   `admin`) and `idSites`. Note that Matomo requires `passwordConfirmation` on
   permission-changing calls — the acting user's own password — which means this step
   generally cannot be automated with a token alone.

7. **Confirm tracking is live.**
   `Live.getCounters` with `idSite` and `lastMinutes=30` gives near-real-time counts
   without waiting for archiving. Then `VisitsSummary.getVisits` with `period=day`,
   `date=today` once data has archived.

## Notes

- `Live.*` is rate limited harder than the rest of the API on Matomo Cloud: 200
  requests/minute per IP, and it counts against the 8-simultaneous-query cap on raw-data
  resources. Poll it politely.
- Reports may be empty immediately after tracking starts because Matomo archives on a
  schedule (or on request). Absence of data in `VisitsSummary` is not proof that the
  tag is broken — `Live.getCounters` is the better liveness check.
- None of these operations have a dedicated MCP tool. An agent can only perform this
  flow if an administrator has enabled raw API create access. See
  `mcp/matomo-tool-crosswalk.yml`.
