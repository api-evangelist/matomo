# Matomo

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Matomo is an open source web analytics platform — self-hosted (Matomo On-Premise) or vendor-hosted (Matomo Cloud) — that gives an organisation complete ownership of its analytics data. Formerly Piwik, it is the leading privacy-first alternative to Google Analytics, with GDPR tooling, data residency in Frankfurt for Cloud, and no data sampling. Its API surface is substantial and unusual: 556 documented operations across 59 plugin modules, every one dispatched through a single /index.php RPC entrypoint on the customer's own deployment rather than a vendor host, plus a separate tracking entrypoint at /matomo.php. Matomo generates its own OpenAPI 3.1.0 documents through a first-party ApiReference plugin, and ships a first-party Model Context Protocol server exposing 19 agent tools over an authenticated HTTP endpoint.

**Areas:** Analytics · Web Analytics · Open Source · Privacy · Data Ownership · Self-Hosted · GDPR · Tag Management · Conversion Optimization · MCP

## Matomo on APIs.io

Everything profiled for Matomo is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/matomo/](https://apis.io/providers/matomo/)** — or go straight to one of the APIs or properties below.

### APIs (60)

- [Matomo Reporting API (index.php entrypoint)](https://apis.io/apis/matomo/matomo-index-php-api/) — The single /index.php dispatch entrypoint through which every Matomo Reporting API method is invoked, by supplying module=API and method=Module.Action. This…
- [Matomo Tracking API (matomo.php entrypoint)](https://apis.io/apis/matomo/matomo-matomo-php-api/) — The Matomo Tracking API — the server-side ingest entrypoint at /matomo.php that records pageviews, events, goals, ecommerce orders, site searches and…
- [Matomo Actions API](https://apis.io/apis/matomo/matomo-actions-api/) — The Actions API lets you request reports for all your Visitor Actions: Page URLs, Page titles, Events, Content Tracking, File Downloads and Clicks on…
- [Matomo Advertising Conversion Export API](https://apis.io/apis/matomo/matomo-advertisingconversionexport-api/) — Exposes API endpoints for managing advertising conversion export configurations. These methods let users list, inspect, create, update, and delete…
- [Matomo Annotations API](https://apis.io/apis/matomo/matomo-annotations-api/) — Provides API methods to create, update, delete, and query annotations.
- [Matomo Bandwidth API](https://apis.io/apis/matomo/matomo-bandwidth-api/) — Exposes reporting API endpoints for aggregated bandwidth metrics.
- [Matomo Cohorts API](https://apis.io/apis/matomo/matomo-cohorts-api/) — Exposes cohort reports grouped by the period of a visitor's first visit. These endpoints transform archived first-visit cohort data into table and chart…
- [Matomo Contents API](https://apis.io/apis/matomo/matomo-contents-api/) — The Contents API exposes content tracking reports grouped by content name and content piece.
- [Matomo Core Admin Home API](https://apis.io/apis/matomo/matomo-coreadminhome-api/) — Provides administrative API methods for scheduling, archiving, tracking failures, and opt-out code generation.
- [Matomo Crash Analytics API](https://apis.io/apis/matomo/matomo-crashanalytics-api/) — Exposes Crash Analytics endpoints for managing tracked crashes and querying crash reports. Includes summary, drill-down, historical, and realtime reporting…
- [Matomo Custom Alerts API](https://apis.io/apis/matomo/matomo-customalerts-api/) — Exposes Custom Alerts API endpoints for managing alert definitions and reading triggered alert data. These methods let callers create, update, fetch,…
- [Matomo Custom Dimensions API](https://apis.io/apis/matomo/matomo-customdimensions-api/) — The Custom Dimensions API lets you manage and access reports for your configured Custom Dimensions.
- [Matomo Custom Js Tracker API](https://apis.io/apis/matomo/matomo-customjstracker-api/) — Provides API methods for custom JavaScript tracker configuration.
- [Matomo Dashboard API](https://apis.io/apis/matomo/matomo-dashboard-api/) — The Dashboard API lets you manage user dashboards and retrieve their widget configurations.
- [Matomo Device Plugins API](https://apis.io/apis/matomo/matomo-deviceplugins-api/) — The DevicePlugins API lets you access reports about device plugins such as browser plugins.
- [Matomo Devices Detection API](https://apis.io/apis/matomo/matomo-devicesdetection-api/) — The DevicesDetection API lets you access reports about your visitors' device types, brands, models, operating systems, and browsers.
- [Matomo Events API](https://apis.io/apis/matomo/matomo-events-api/) — The Events API lets you request reports about your users' Custom Events. Events are tracked using the Javascript Tracker trackEvent() function, or using the…
- [Matomo Feedback API](https://apis.io/apis/matomo/matomo-feedback-api/) — Provides API methods for submitting product feedback and managing feedback reminders.
- [Matomo Form Analytics API](https://apis.io/apis/matomo/matomo-formanalytics-api/) — Exposes the Form Analytics API for managing tracked forms and retrieving form performance reports. Use these endpoints to create, update, archive, and…
- [Matomo Funnels API](https://apis.io/apis/matomo/matomo-funnels-api/) — Exposes the Funnels reporting and management API for funnel analytics configuration. Includes endpoints for funnel reports, funnel definitions, and pattern…
- [Matomo Goals API](https://apis.io/apis/matomo/matomo-goals-api/) — Goals API lets you Manage existing goals, via "updateGoal" and "deleteGoal", create new Goals via "addGoal", or list existing Goals for one or several…
- [Matomo Heatmap Session Recording API](https://apis.io/apis/matomo/matomo-heatmapsessionrecording-api/) — Exposes the Heatmap & Session Recording API endpoints for managing configurations and retrieving recorded activity. Heatmap coordinates use relative values:…
- [Matomo Image Graph API](https://apis.io/apis/matomo/matomo-imagegraph-api/) — The ImageGraph.get API call lets you generate beautiful static PNG Graphs for any existing Matomo report. Supported graph types are: line plot, 2D/3D pie…
- [Matomo Insights API](https://apis.io/apis/matomo/matomo-insights-api/) — Provides API methods for insight and mover/shaker comparisons between report periods.
- [Matomo Languages Manager API](https://apis.io/apis/matomo/matomo-languagesmanager-api/) — The LanguagesManager API lets you access existing Matomo translations, and change Users languages preferences. "getTranslationsForLanguage" will return all…
- [Matomo Live API](https://apis.io/apis/matomo/matomo-live-api/) — The Live! API lets you access complete visit level information about your visitors. Combined with the power of <a…
- [Matomo Login API](https://apis.io/apis/matomo/matomo-login-api/) — Provides API methods for login-related administration tasks.
- [Matomo Marketing Campaigns Reporting API](https://apis.io/apis/matomo/matomo-marketingcampaignsreporting-api/) — Exposes reporting API endpoints for marketing campaign dimensions and drill-down reports. Includes campaign IDs, names, keywords, source and medium…
- [Matomo Marketplace API](https://apis.io/apis/matomo/matomo-marketplace-api/) — The Marketplace API lets you manage your license key so you can download & install in one-click <a target="_blank" rel="noreferrer"…
- [Matomo Media Analytics API](https://apis.io/apis/matomo/matomo-mediaanalytics-api/) — Exposes Media Analytics reports for video and audio plays, engagement, resources, and player usage. Includes real-time endpoints for recent activity and…
- [Matomo Mobile Messaging API](https://apis.io/apis/matomo/matomo-mobilemessaging-api/) — The MobileMessaging API lets you manage SMS credentials, phone number verification, and SMS account settings.
- [Matomo Multi Sites API](https://apis.io/apis/matomo/matomo-multisites-api/) — The MultiSites API lets you request the key metrics (visits, page views, revenue) for all Websites in Matomo.
- [Matomo Overlay API](https://apis.io/apis/matomo/matomo-overlay-api/) — The Overlay API exposes translation data and overlay-specific page transition reports.
- [Matomo Page Performance API](https://apis.io/apis/matomo/matomo-pageperformance-api/) — Provides reporting API methods for aggregated page performance metrics.
- [Matomo Privacy Manager API](https://apis.io/apis/matomo/matomo-privacymanager-api/) — The PrivacyManager API lets you manage GDPR workflows, anonymization settings, and privacy compliance controls.
- [Matomo Referrers API](https://apis.io/apis/matomo/matomo-referrers-api/) — The Referrers API lets you access reports about websites, search engines, keywords, social networks, AI assistants, and campaigns used to access your…
- [Matomo Resolution API](https://apis.io/apis/matomo/matomo-resolution-api/) — Provides API methods for screen resolution and device configuration reports.
- [Matomo Roll Up Reporting API](https://apis.io/apis/matomo/matomo-rollupreporting-api/) — Provides API endpoints for managing roll-up websites and their source site assignments. Use these methods to create roll-ups, update their configuration,…
- [Matomo Search Engine Keywords Performance API](https://apis.io/apis/matomo/matomo-searchenginekeywordsperformance-api/) — Provides SearchEngineKeywordsPerformance API endpoints for imported keyword and crawl-performance reports. Exposes combined and provider-specific reports…
- [Matomo Segment Editor API](https://apis.io/apis/matomo/matomo-segmenteditor-api/) — The SegmentEditor API lets you add, update, delete custom Segments, and list saved segments.
- [Matomo SEO API](https://apis.io/apis/matomo/matomo-seo-api/) — The SEO API lets you access a list of SEO metrics for the specified URL: Bing indexed pages and age of the Domain name.
- [Matomo Sites Manager API](https://apis.io/apis/matomo/matomo-sitesmanager-api/) — The SitesManager API gives you full control on Websites in Matomo (create, update and delete), and many methods to retrieve websites based on various…
- [Matomo Tour API](https://apis.io/apis/matomo/matomo-tour-api/) — Provides API methods for Tour challenges and engagement levels.
- [Matomo Transitions API](https://apis.io/apis/matomo/matomo-transitions-api/) — Provides API methods for transition reports around a specific page action.
- [Matomo User Country API](https://apis.io/apis/matomo/matomo-usercountry-api/) — The UserCountry API lets you access reports about your visitors' Countries and Continents.
- [Matomo User ID API](https://apis.io/apis/matomo/matomo-userid-api/) — Provides API methods for User ID reports.
- [Matomo User Language API](https://apis.io/apis/matomo/matomo-userlanguage-api/) — The UserLanguage API lets you access reports about your Visitors language setting
- [Matomo Users Manager API](https://apis.io/apis/matomo/matomo-usersmanager-api/) — The UsersManager API lets you Manage Users and their permissions to access specific websites. You can create users via "addUser", update existing users via…
- [Matomo Visit Frequency API](https://apis.io/apis/matomo/matomo-visitfrequency-api/) — VisitFrequency API lets you access a list of metrics related to Returning Visitors.
- [Matomo Visitor Interest API](https://apis.io/apis/matomo/matomo-visitorinterest-api/) — VisitorInterest API lets you access visitor engagement distribution reports, including visits by pages viewed, visit duration, days since last visit, and…
- [Matomo Visits Summary API](https://apis.io/apis/matomo/matomo-visitssummary-api/) — VisitsSummary API lets you access the core web analytics metrics (visits, unique visitors, count of actions (page views & downloads & clicks on outlinks),…
- [Matomo Visit Time API](https://apis.io/apis/matomo/matomo-visittime-api/) — VisitTime API lets you access reports by Hour (Server time), and by Hour Local Time of your visitors.
- [Matomo O Auth2 API](https://apis.io/apis/matomo/matomo-oauth2-api/) — Exposes super-user OAuth2 client management endpoints for Matomo. This API lists configured scopes and lets administrators create, inspect, update, rotate,…
- [Matomo Ab Testing API](https://apis.io/apis/matomo/matomo-ab-testing-api/) — Exposes the AbTesting API for managing experiments, embedding experiment scripts, and reading experiment reports.
- [Matomo Activity Log API](https://apis.io/apis/matomo/matomo-activity-log-api/) — Exposes Activity Log API endpoints for listing activity entries, counting matches, and resolving the permitted date range for the current caller.
- [Matomo API Reference API](https://apis.io/apis/matomo/matomo-api-reference-api/) — Provides Reporting API endpoints for reading OpenAPI plugin configuration and specifications. Exposes endpoints to return the effective plugin list for spec…
- [Matomo Custom Reports API](https://apis.io/apis/matomo/matomo-custom-reports-api/) — Exposes Custom Reports configuration and reporting endpoints. Use it to create, duplicate, manage, and query custom report definitions and their archived data.
- [Matomo Scheduled Reports API](https://apis.io/apis/matomo/matomo-scheduled-reports-api/) — The ScheduledReports API lets you manage Scheduled Email reports, as well as generate, download or email any existing report.
- [Matomo Tag Manager API](https://apis.io/apis/matomo/matomo-tag-manager-api/) — Exposes the Tag Manager API for managing containers, versions, tags, triggers, and variables. The endpoints also provide installation metadata, publishing…
- [Matomo Two Factor Auth API](https://apis.io/apis/matomo/matomo-two-factor-auth-api/) — Provides API methods for managing two-factor authentication.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [matomo](https://apis.io/servers/matomo/matomo/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Matomo Agentic Access](https://apis.io/agentic-access/matomo/matomo-agentic-access/)

#### Collections (4)

Postman and Open Collection request collections.

- [Matomo Reporting API](https://apis.io/collections/matomo/open-matomo/)
- [Matomo Reporting Index.php API](https://apis.io/collections/matomo/open-matomo-index-php-api/)
- [Matomo Reporting Index.php Matomo.php API](https://apis.io/collections/matomo/open-matomo-matomo-php-api/)
- [Matomo Tracking API](https://apis.io/collections/matomo/open-matomo-tracking/)

#### Overlays (119)

OpenAPI overlays, including conversational phrasing for each operation.

- [Matomo Ab Testing Api Phrasing Overlay](https://apis.io/overlays/matomo/matomo-ab-testing-api-phrasing-overlay/)
- [Matomo Ab Testing Overlay](https://apis.io/overlays/matomo/matomo-ab-testing-overlay/)
- [Matomo Actions Api Phrasing Overlay](https://apis.io/overlays/matomo/matomo-actions-api-phrasing-overlay/)
- [Matomo Actions Overlay](https://apis.io/overlays/matomo/matomo-actions-overlay/)
- [Matomo Activity Log Api Phrasing Overlay](https://apis.io/overlays/matomo/matomo-activity-log-api-phrasing-overlay/)
- [Matomo Activity Log Overlay](https://apis.io/overlays/matomo/matomo-activity-log-overlay/)
- [Matomo Advertising Conversion Export Overlay](https://apis.io/overlays/matomo/matomo-advertising-conversion-export-overlay/)
- [Matomo Advertisingconversionexport Api Phrasing Overlay](https://apis.io/overlays/matomo/matomo-advertisingconversionexport-api-phrasing-overlay/)
- [Matomo Annotations Api Phrasing Overlay](https://apis.io/overlays/matomo/matomo-annotations-api-phrasing-overlay/)
- [Matomo Annotations Overlay](https://apis.io/overlays/matomo/matomo-annotations-overlay/)
- [Matomo Api Overlay](https://apis.io/overlays/matomo/matomo-api-overlay/)
- [Matomo Api Reference Api Phrasing Overlay](https://apis.io/overlays/matomo/matomo-api-reference-api-phrasing-overlay/)
- [Matomo Api Reference Overlay](https://apis.io/overlays/matomo/matomo-api-reference-overlay/)
- [Matomo Bandwidth Api Phrasing Overlay](https://apis.io/overlays/matomo/matomo-bandwidth-api-phrasing-overlay/)
- [Matomo Bandwidth Overlay](https://apis.io/overlays/matomo/matomo-bandwidth-overlay/)
- [Matomo Cohorts Api Phrasing Overlay](https://apis.io/overlays/matomo/matomo-cohorts-api-phrasing-overlay/)
- [Matomo Cohorts Overlay](https://apis.io/overlays/matomo/matomo-cohorts-overlay/)
- [Matomo Contents Api Phrasing Overlay](https://apis.io/overlays/matomo/matomo-contents-api-phrasing-overlay/)
- [Matomo Contents Overlay](https://apis.io/overlays/matomo/matomo-contents-overlay/)
- [Matomo Core Admin Home Overlay](https://apis.io/overlays/matomo/matomo-core-admin-home-overlay/)
- [Matomo Coreadminhome Api Phrasing Overlay](https://apis.io/overlays/matomo/matomo-coreadminhome-api-phrasing-overlay/)
- [Matomo Crash Analytics Overlay](https://apis.io/overlays/matomo/matomo-crash-analytics-overlay/)
- [Matomo Crashanalytics Api Phrasing Overlay](https://apis.io/overlays/matomo/matomo-crashanalytics-api-phrasing-overlay/)
- [Matomo Custom Alerts Overlay](https://apis.io/overlays/matomo/matomo-custom-alerts-overlay/)
- [Matomo Custom Dimensions Overlay](https://apis.io/overlays/matomo/matomo-custom-dimensions-overlay/)
- …and 94 more published on APIs.io

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Matomo Authentication](https://apis.io/security/matomo/matomo-authentication/)
- [Matomo Domain Security](https://apis.io/security/matomo/matomo-domain-security/)
- [Matomo Trust Center](https://apis.io/security/matomo/matomo-trust-center/)
- [Matomo Vulnerability Disclosure](https://apis.io/security/matomo/matomo-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Matomo Scopes](https://apis.io/scopes/matomo/matomo-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Matomo Plans Pricing](https://apis.io/plans/matomo/matomo-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Matomo Rate Limits](https://apis.io/rate-limits/matomo/matomo-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Matomo Finops](https://apis.io/finops/matomo/matomo-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://matomo.org)
- [Documentation](https://developer.matomo.org)
- [Getting started](https://developer.matomo.org/guides/getting-started-part-1)
- [API reference](https://developer.matomo.org/api-reference/api)
- [Pricing](https://matomo.org/pricing/)
- [Sign up](https://matomo.org/start-free-analytics-trial)
- [Support](https://matomo.org/support)
- [Blog](https://matomo.org/blog)
- [Security](https://matomo.org/security/)
- [Compliance](https://matomo.org/security/)
- [Terms of service](https://matomo.org/terms)
- [Privacy policy](https://matomo.org/privacy-policy)
- [GitHub](https://github.com/matomo-org)
- [Status](https://status.matomo.cloud/)

## API Evangelist rating

**Kin Score 69.0** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.3 |
| Contract quality | 49.0 |
| Contract governance | 4.5 |
| Operational transparency | 81.6 |
| Developer ergonomics | 80.4 |
| Access clarity | 92.1 |

**Agent readiness 37.4** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | templated |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 45.1** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/matomo/](https://apis.io/providers/matomo/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Matomo: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/matomo/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
