# Matomo (matomo)

Matomo is an open source web analytics platform that provides comprehensive website and application usage analytics with full data ownership. Formerly known as Piwik, it offers an alternative to Google Analytics with on-premise or cloud hosting options, ensuring complete control over analytics data and compliance with privacy regulations including GDPR.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/matomo/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/matomo/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Analytics
- Data Ownership
- Open Source
- Privacy
- Self-Hosted
- Web Analytics

## Timestamps

- **Created:** 2026-03-26
- **Modified:** 2026-05-30

## APIs

### Matomo Reporting API

The Matomo Reporting API provides programmatic access to all analytics reports available in the Matomo interface. It exposes over 200 API methods organized into modules such as VisitsSummary, Actions, Referrers, UserCountry, DevicesDetection, Goals, and more. Each module provides methods to retrieve metrics, dimensions, and segmented data for building custom dashboards and reporting tools.

- **Human URL:** [https://developer.matomo.org/api-reference/reporting-api](https://developer.matomo.org/api-reference/reporting-api)

#### Tags

- Analytics
- Dashboards
- Metrics
- Reporting

#### Properties

- [Documentation](https://developer.matomo.org/api-reference/reporting-api)
- [Getting Started](https://developer.matomo.org/api-reference/reporting-api-introduction)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/matomo/refs/heads/main/openapi/matomo-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/matomo-tracking.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/matomo-tracking.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/matomo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/matomo.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Matomo Tracking API

The Matomo Tracking API allows developers to send tracking data to Matomo from any server-side application, mobile app, or IoT device via HTTP requests. It supports recording pageviews, custom events, e-commerce transactions, content interactions, site search queries, and custom dimensions. The API also supports bulk tracking for sending multiple events in a single request.

- **Human URL:** [https://developer.matomo.org/api-reference/tracking-api](https://developer.matomo.org/api-reference/tracking-api)

#### Tags

- Analytics
- Events
- Server-Side
- Tracking

#### Properties

- [Documentation](https://developer.matomo.org/api-reference/tracking-api)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/matomo/refs/heads/main/openapi/matomo-tracking-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/matomo-tracking.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/matomo-tracking.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/matomo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/matomo.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Matomo Live API

The Matomo Live API provides real-time access to visitor data including the most recent visits, visitor profiles, and live counters showing current visitors on the site. It enables developers to build real-time dashboards, visitor activity feeds, and monitoring tools that display up-to-the-minute analytics data.

- **Human URL:** [https://developer.matomo.org/api-reference/reporting-api#Live](https://developer.matomo.org/api-reference/reporting-api#Live)

#### Tags

- Analytics
- Live Data
- Real-Time
- Visitors

#### Properties

- [Documentation](https://developer.matomo.org/api-reference/reporting-api#Live)
- [Postman Collection](collections/matomo-tracking.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/matomo-tracking.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/matomo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/matomo.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Matomo Goals API

The Matomo Goals API allows developers to manage and retrieve data about conversion goals. It supports creating, updating, and deleting goals, as well as retrieving goal conversion metrics, revenue data, and conversion rates segmented by various dimensions such as referrer, country, and device type.

- **Human URL:** [https://developer.matomo.org/api-reference/reporting-api#Goals](https://developer.matomo.org/api-reference/reporting-api#Goals)

#### Tags

- Analytics
- Conversions
- Goals
- Revenue

#### Properties

- [Documentation](https://developer.matomo.org/api-reference/reporting-api#Goals)
- [Postman Collection](collections/matomo-tracking.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/matomo-tracking.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/matomo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/matomo.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Matomo Segments API

The Matomo Segments API enables developers to create and manage saved segments for filtering analytics data. Segments allow filtering visits and actions by any combination of visitor properties, behavior patterns, and custom dimensions. Any Reporting API method can accept a segment parameter to return data for a specific subset of visitors.

- **Human URL:** [https://developer.matomo.org/api-reference/reporting-api-segmentation](https://developer.matomo.org/api-reference/reporting-api-segmentation)

#### Tags

- Analytics
- Filters
- Segmentation
- Visitors

#### Properties

- [Documentation](https://developer.matomo.org/api-reference/reporting-api-segmentation)
- [Postman Collection](collections/matomo-tracking.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/matomo-tracking.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/matomo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/matomo.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/matomo)
- [Website](https://matomo.org)
- [Documentation](https://developer.matomo.org)
- [A P I Documentation](https://developer.matomo.org/api-reference/reporting-api)
- [Getting Started](https://developer.matomo.org/guides/getting-started-part-1)
- [Blog](https://matomo.org/blog)
- [Pricing](https://matomo.org/pricing)
- [Git Hub](https://github.com/matomo-org/matomo)
- [Login](https://matomo.org/login)
- [Sign Up](https://matomo.org/start-free-analytics-trial)
- [Support](https://matomo.org/support)
- [Forum](https://forum.matomo.org)
- [Marketplace](https://plugins.matomo.org)
- [Self Hosted](https://matomo.org/matomo-on-premise)
- [Changelog](https://matomo.org/changelog)
- [S D Ks](https://developer.matomo.org/api-reference/tracking-api-clients)
- [Terms of Service](https://matomo.org/terms)
- [Privacy Policy](https://matomo.org/privacy-policy)
- [Integrations](https://matomo.org/guide/tracking-data/integrations/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
