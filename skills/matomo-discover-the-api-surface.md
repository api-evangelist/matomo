---
name: Discover a Matomo instance's actual API surface
description: >-
  Before calling anything, find out what THIS Matomo deployment exposes. Matomo is
  self-hosted or Matomo Cloud, and its API surface is determined by the version
  installed and the plugins activated — so the method you need may simply not exist
  on the instance in front of you.
api: openapi/matomo-api-openapi.json
operations:
  - API.getMatomoVersion
  - API.getReportMetadata
  - API.getMetadata
  - API.isPluginActivated
  - API.getSegmentsMetadata
  - ApiReference.getOpenApiSpec
  - SitesManager.getSitesWithAtLeastViewAccess
---

# Discover a Matomo instance's actual API surface

## Why this comes first

There is no single "the Matomo API". Every deployment is different. Two instances on
the same Matomo release expose different methods because different plugins are
activated. Assuming a method exists is the most common way a Matomo integration fails,
and it fails as a `404 — The method is not available.`

## Ground rules

- Every call goes to `https://{matomo_host}/index.php?module=API&method=<Module>.<Action>`.
- **Always send `format=json`.** The default response format is `xml`.
- Authenticate with the Matomo auth token. Prefer POST with `token_auth` in the body,
  or an `Authorization: Bearer <token_auth>` header. Avoid the query string — it lands
  in access logs.
- An error can arrive with HTTP 200. Check `result` in the body, not just the status.

## Steps

1. **Confirm you are talking to Matomo and learn its version.**
   Call `API.getMatomoVersion`. A version string back means the entrypoint is live and
   your token (if sent) parsed. This is the cheapest possible health check.

2. **List the sites you can actually see.**
   Call `SitesManager.getSitesWithAtLeastViewAccess`. Everything downstream needs an
   `idSite`, and this returns exactly the sites your token's user is permitted to read.
   Do not call `SitesManager.getAllSites` unless you know you hold superuser access —
   it will 403 otherwise.

3. **Pull the report catalog for a site.**
   Call `API.getReportMetadata` with `idSite`. This is the authoritative, machine-readable
   list of every report that exists on this instance, with its module, action, dimension,
   metrics and metric documentation. Treat it as the index; do not hardcode report names.

4. **Check for a specific capability before you depend on it.**
   Call `API.isPluginActivated` with the plugin name (for example `Funnels`,
   `CustomReports`, `McpServer`, `ApiReference`). This turns a would-be 404 into a
   yes/no you can branch on.

5. **If the ApiReference plugin is activated, take the contract itself.**
   Call `ApiReference.getOpenApiSpec` with `pluginName=<Plugin>` and `format=json`. It
   returns a generated OpenAPI 3.1.0 document for that plugin — operation ids,
   parameter descriptions, response codes. This is the single best thing to feed a
   downstream agent, and it is how the 59 specs in `openapi/` in this repo were
   obtained.

6. **Learn what you can segment on.**
   Call `API.getSegmentsMetadata` with `idSite` to get the valid segment dimensions for
   this instance before you try to build a `segment=` expression.

## Notes

- The generated OpenAPI documents deviate from the specification in two known ways:
  path keys contain a query string, and some `content` entries serialize as empty
  arrays. Parse them as JSON; do not run them through a strict OpenAPI validator and
  conclude the instance is broken.
- See `conventions/matomo-conventions.yml` for pagination and response-format rules,
  and `errors/matomo-problem-types.yml` for the error envelope.
