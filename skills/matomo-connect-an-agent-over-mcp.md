---
name: Connect an agent to Matomo over MCP
description: >-
  Set up and call Matomo's first-party MCP server so an AI agent can query analytics in
  natural language, including the OAuth flow and the administrator gates that decide
  which tools an agent actually sees.
api: mcp/matomo-mcp.yml
operations:
  - McpServer.mcp
  - OAuth2.getClients
  - UsersManager.createAppSpecificTokenAuth
  - API.isPluginActivated
---

# Connect an agent to Matomo over MCP

Matomo ships a first-party MCP server as the `McpServer` plugin. It is a **remote**
server — an MCP client POSTs JSON-RPC to an HTTPS endpoint — but the endpoint belongs to
the customer's own Matomo instance. There is no vendor-hosted Matomo MCP URL.

## The endpoint

```
https://{matomo_host}/index.php?module=API&method=McpServer.mcp&format=mcp
```

`format=mcp` is required. The endpoint is root-request-only: nested or proxied calls,
including `API.getBulkRequest`, are rejected with `400`.

## Prerequisites

- **Matomo Cloud**: the MCP server is included.
- **Matomo On-Premise**: install the `McpServer` plugin, activate it in
  *Administration → Plugins*, then enable MCP in
  *Administration → System → General Settings → McpServer*. Requires Matomo ≥ 5.8.0 and
  PHP ≥ 8.1.
- Confirm programmatically with `API.isPluginActivated` (`pluginName=McpServer`).
- **MCP access is disabled by default.** A 401 that never resolves usually means it was
  never switched on, not that your credential is wrong.

## Authenticate

Two options, both sent as an HTTP **Bearer** token:

1. **OAuth 2.0 (recommended).** Requires the Matomo `OAuth2` plugin and a configured
   client. Discover the endpoints anonymously at
   `https://{matomo_host}/.well-known/oauth-authorization-server` — it returns RFC 8414
   metadata with the authorize and token URLs, PKCE methods (`S256`, `plain`) and the
   scopes `matomo:read`, `matomo:write`, `matomo:admin`. Access tokens default to a
   3600-second lifetime.
2. **Matomo `token_auth` as a Bearer token.** Create one in
   *Administration → Personal → Security → Auth tokens*, or via
   `UsersManager.createAppSpecificTokenAuth`.

Either way the credential inherits the full permissions of the Matomo user behind it.
To give an agent least privilege, **create a dedicated Matomo user with view access to
only the sites it should see, and mint the token as that user.** There is no way to
narrow a token or an OAuth scope below the user's own role.

## What the agent will see

Twelve tools are always available once MCP is on:

- Sites — `matomo_site_list`, `matomo_site_get`, `matomo_site_search`
- Reports — `matomo_report_list`, `matomo_report_metadata`, `matomo_report_processed`
- Goals — `matomo_goal_list`, `matomo_goal_get`
- Segments — `matomo_segment_list`, `matomo_segment_get`
- Dimensions — `matomo_dimension_list`, `matomo_dimension_get`

Seven more are **hidden by default** and only appear if an administrator raises
*Raw Matomo API tool access*: `matomo_api_list`, `matomo_api_get`, and the executors
`matomo_api_call_read` / `_create` / `_update` / `_delete` / `_full`. Read, Create,
Update and Delete are independent checkboxes — enabling Create does not enable Read.

## The normal flow

1. `matomo_site_search` or `matomo_site_list` → get an `idSite`.
2. `matomo_report_list` with `idSite` (and a `search` filter) → find the report.
3. `matomo_report_metadata` → confirm the selector and its parameters.
4. `matomo_report_processed` → get the rows.

Tools paginate with `limit` and an opaque `cursor` — **not** with `filter_limit` /
`filter_offset`. That is an MCP-layer convention that does not match the REST API.

## Things that will bite you

- `matomo_report_processed` is declared **non-idempotent**, and its `readOnlyHint` is
  computed at runtime — materializing a range aggregate can trigger archiving, which is
  a write. Do not assume "reading a report" is free.
- Sending an `Origin` header outside the instance's `[General] trusted_hosts` gets a
  `403`. Browser-based MCP clients are not supported at all: there is no preflight
  handling and a CORS `OPTIONS` arrives without the Bearer token. Connect from a native
  MCP client or a same-origin backend.
- The instance serves no `/.well-known/oauth-protected-resource`, so an MCP client
  cannot auto-discover the authorization server from the resource — configure the
  authorization server explicitly.
- Tracking is not on the agent surface at all. An agent can read analytics through MCP;
  it cannot write tracking events.
