---
title: "Custom dimensions: Setup and implementation guide"
url: "https://matomo.org/blog/2026/03/custom-dimensions/"
date: "Fri, 06 Mar 2026 18:59:04 +0000"
author: "Joe Maurer"
feed_url: "https://matomo.org/blog/feed/"
---
<p>Websites generate an endless stream of behaviour signals each day. Page views, traffic sources and bounce rates paint part of the picture, yet the deeper story often remains hidden. Campaigns may succeed with one group but fall flat with another, and content that drives strong engagement in one segment may barely register in the next.</p>



<p>This gap between what happened and why it happened is a common challenge in analytics. Standard dashboards surface general patterns but struggle to explain their context.</p>



<p>Custom dimensions offer a way to capture that missing context by attaching meaningful attributes to visits and actions. Details, such as user roles, content categories or subscription tiers, can transform raw activity into insight.&nbsp;</p>



<p>This article explores what custom dimensions are, how they work in Matomo and how to set them up for clearer, more relevant reporting.<br /></p>



<h2 class="wp-block-heading">What are custom dimensions?</h2>



<p>Custom dimensions are extra pieces of information attached to visits or actions in an analytics tool. Instead of relying only on default fields, such as page URL or traffic source, an analyst can store tailored attributes that matter to the business, then use them in reports for deeper insight.</p>



<p>Each custom dimension holds a name and a value. During tracking, the value is sent with the hit, and Matomo stores it alongside standard metrics. When reports run, Matomo groups and filters data by these values, which keeps the analysis accurate and consistent.</p>



<p>For example, a “subscription tier” custom dimension can record whether a visitor is on a Free, Pro or Enterprise plan. Another might capture “Content type,” such as article, video or product page.&nbsp;</p>



<p>Custom dimensions can be set up to avoid personal data, which helps teams measure behaviour without tracking names or contact details. They also give analysts more say in how results are grouped in reports.</p>



<h2 class="wp-block-heading">Common use cases</h2>



<p>Custom dimensions are most useful when they add context that standard metrics miss. The examples below show how a few extra fields can turn log data into clear, practical findings.</p>



<h3 class="wp-block-heading">Content performance tracking</h3>



<p>Editors can tag visits with content author, category or content type. Reports then reveal which authors keep visitors engaged, which categories attract new audiences and whether articles, videos or product pages drive the most conversions.</p>



<h3 class="wp-block-heading">User segmentation</h3>



<p>Marketers often track subscription tier, user type or acquisition channel as custom dimensions. A tier such as Free, Pro or Enterprise can be followed through funnels to compare feature usage, upgrade rates and campaign performance with clear, transparent splits.</p>



<figure class="wp-block-image size-large"><img alt="An image showing the common use cases of Matomo&#039;s custom dimensions" class="wp-image-91206" height="586" src="https://matomo.org/wp-content/uploads/2026/03/Common-Custom-Dimension-Use-Cases-1024x586.png" width="1024" /></figure>



<h3 class="wp-block-heading"><br />Ecommerce insights </h3>



<p>Stores can attach product attributes, such as brand or collection, along with the customer lifetime value band. That makes it easier to compare groups that spend more or stay longer, without storing personal data.</p>



<h3 class="wp-block-heading">Technical tracking&nbsp;</h3>



<p>Teams can record a page load time band or an error type. Lining those values up against clicks and conversions shows where slow pages or repeating errors cause visitors to drop off.</p>



<h2 class="wp-block-heading">Implementing and managing custom dimensions</h2>



<p>Implementing custom dimensions in Matomo follows two stages: define the dimension, then send values with each relevant hit. A little planning at this point protects accuracy, performance and privacy later.</p>



<h3 class="wp-block-heading">Step 1: Plan and create the dimension</h3>



<p>Before creating a new dimension, teams decide whether it should describe an entire visit (visit-scoped) or a single interaction, such as a page view or event (action-scoped).&nbsp;</p>



<p>In Matomo, administrators click:&nbsp;</p>



<ul class="wp-block-list">
<li>The Administration page (cog icon)</li>



<li>Measurables or Websites (depending on setup) in the left-side menu</li>



<li>Custom Dimensions</li>
</ul>



<p>They can then add a name, choose the scope and set the dimension as active.&nbsp;</p>



<p>Because each site has a limited number of slots per scope and&nbsp;<a href="https://matomo.org/faq/reports/how-to-delete-a-dimension/">dimensions usually can’t be deleted</a>, only deactivated, most teams reserve them for stable concepts, such as subscription tier or content group, rather than volatile labels.</p>



<h3 class="wp-block-heading">Step 2: Track values from the site or app</h3>



<p>For sites that use the&nbsp;<a href="https://matomo.org/subcategory/developer-resources-custom-dimensions/">JavaScript tracker</a>, custom dimensions are attached to hits through the&nbsp;<strong>_paq</strong>&nbsp;queue.<br /><br />This simple example records a visitor’s plan:</p>



<figure class="wp-block-table"><table class="has-fixed-layout"><tbody><tr><td class="has-text-align-center">_paq.push([&#8216;setCustomDimension&#8217;, 2, &#8216;Pro&#8217;]);</td></tr></tbody></table></figure>



<p>This call runs before the relevant&nbsp;<strong>trackPageView</strong>&nbsp;or event, and Matomo stores the value alongside the standard metrics for that visit or action.</p>



<p><a href="https://matomo.org/guide/tag-manager/">Matomo Tag Manager</a>&nbsp;offers another route and keeps tracking logic in one place. A variable first captures the value, like a data layer field that holds&nbsp;<strong>userRole</strong>. In the Matomo Configuration Variable, the Custom Dimensions section maps a dimension index to that variable. When a tag that uses this configuration fires, it sends the custom dimension value with the hit. In preview mode, teams can check the container and see those values in the request before publishing any changes.</p>



<p>Server-side systems, background jobs or mobile apps that call the&nbsp;<a href="https://matomo.org/guide/apis/tracking-api/">HTTP Tracking API</a>&nbsp;add custom dimensions with&nbsp;<strong>dimension{id}</strong>&nbsp;parameters, such as&nbsp;<strong>dimension2=Enterprise</strong>. Separate ranges support visit and action scopes, which help keep imports structured and efficient.</p>



<h3 class="wp-block-heading">Step 3: Maintain and validate</h3>



<p>After tracking is live, teams should watch reports and logs for empty rows or odd values.</p>



<p>Action dimensions can also take values from URLs or page titles through extraction rules. That approach cuts down on code edits and makes it clear where each value comes from.</p>



<p>Periodic reviews of active dimensions, along with consent and data minimisation settings, help ensure the implementation remains accurate, privacy-friendly and easy to extend.</p>



<figure class="wp-block-image size-large"><img alt="A graphic representing the steps for Matomo Custom Dimensions" class="wp-image-91208" height="586" src="https://matomo.org/wp-content/uploads/2026/03/Steps-for-Matomo-Custom-Dimensions-1024x586.png" width="1024" /></figure>



<h2 class="wp-block-heading"><br />How custom dimensions affect analytics and reporting</h2>



<p>Once custom dimensions begin collecting data, they become part of Matomo’s standard reporting flow.&nbsp;</p>



<p>Each dimension&nbsp;<a href="https://matomo.org/faq/reporting-tools/view-a-custom-dimension-report/">appears in dedicated reports</a>&nbsp;where metrics are grouped by the stored values. It keeps analysis consistent and makes it clear how attributes (like subscription tier or content type) relate to behaviour and results.</p>



<p>Matomo processes&nbsp;<a href="https://matomo.org/faq/understanding-visits-and-action-levels-in-matomo/">visit-scoped and action-scoped dimensions</a>&nbsp;differently:</p>



<ul class="wp-block-list">
<li><strong>Visit-level dimensions</strong>&nbsp;describe the whole session, so reports summarise complete visits and conversions by each value.&nbsp;</li>



<li><a href="https://matomo.org/faq/reporting-tools/segment-a-custom-dimension-by-action-type/"><strong>Action-level dimensions</strong></a>&nbsp;attach to individual events, page views or downloads. In these reports, a single visit can contribute multiple rows, which helps expose detailed patterns, like which content category generated the most downloads or form submissions.</li>
</ul>



<p>Custom dimensions can also feed Custom Reports. Analysts can add a dimension as a row or column, then filter by action type to focus on events, downloads or other specific interactions. This level of control, combined with clear scopes, supports accurate reporting and efficient workflows without obscuring how Matomo stores and processes the underlying data.</p>



<h2 class="wp-block-heading">Privacy and compliance considerations</h2>



<p>Custom dimensions can touch personal data, depending on implementation, so they form an important part of privacy and compliance work.</p>



<p>Under&nbsp;<a href="https://matomo.org/blog/2025/03/data-privacy-regulations-essential-knowledge-for-global-business/">GDPR and similar laws</a>, any field that can identify or single out a person needs a lawful basis, a clear purpose and suitable safeguards. In practice, this means planning dimensions with legal and privacy teams, as well as analysts.</p>



<p>Data minimisation, careful consent management and anonymisation are at the core of a privacy-forward and compliant implementation.</p>



<figure class="wp-block-image size-large"><img alt="An image representing privacy and compliance considerations" class="wp-image-91210" height="586" src="https://matomo.org/wp-content/uploads/2026/03/Privacy-and-Compliance-Considerations-1024x586.png" width="1024" /></figure>



<p><br />For custom dimensions, that often means recording stable, non-identifying values, such as subscription tier or an internal segment label, instead of names or email addresses. It also means linking records with a pseudonymous ID.</p>



<p>Data minimisation keeps each dimension tied to a single purpose. Retention rules and deletion processes then clear out values once they are no longer needed. Anonymisation and aggregation features in Matomo, including&nbsp;<a href="https://matomo.org/faq/general/configure-privacy-settings-in-matomo/">IP masking</a>&nbsp;and&nbsp;<a href="https://matomo.org/cookie-consent-banners/">optional cookieless tracking</a>, help reduce risk further when combined with explicit consent where required.&nbsp;</p>



<p>Planned this way, custom dimensions support accurate analysis while maintaining transparency, user control and respect for local privacy requirements.</p>



<h2 class="wp-block-heading">Advanced tips and best practices</h2>



<h3 class="wp-block-heading">Reserve slots for stable attributes</h3>



<p>Custom dimension slots are limited and difficult to restructure later, so teams should stick to stable ideas and stay away from ultra-granular values that will bloat tables.</p>



<p>Planning ahead of time and consulting the&nbsp;<a href="https://matomo.org/faq/getting-started/download-the-matomo-measurement-plan/">Matomo Measurement Plan</a>&nbsp;can prevent performance issues or dimension limit frustrations down the road.</p>



<h3 class="wp-block-heading">Avoid high-cardinality values</h3>



<p>High-cardinality dimensions, meaning those that have a large or infinite number of unique values, increase archive time and slow down reporting. Teams should avoid using dynamic values for their dimensions, like time stamps or full URLs with parameters.</p>



<h3 class="wp-block-heading">Keep names simple and consistent</h3>



<p>Naming matters. Simple labels such as “Subscription tier” or “Content category” make reports easier to scan and make future changes less painful.&nbsp;</p>



<p>A shared naming convention for events, custom dimensions and variables helps everyone understand what each field stores and how it shows up in dashboards and exports.</p>



<h2 class="wp-block-heading">Troubleshooting common issues</h2>



<h3 class="wp-block-heading">Data not appearing in reports</h3>



<p>The most common cause of missing data is scope or timing. The dimension must be:&nbsp;</p>



<ul class="wp-block-list">
<li>Active</li>



<li>Attached to the correct site</li>



<li>Sent before&nbsp;<strong>trackPageView</strong>&nbsp;or the relevant event</li>
</ul>



<p>Reports only show data for the selected date range, so very recent hits may appear first in real-time or visit logs before they reach aggregated reports.</p>



<h3 class="wp-block-heading">“undefined” or “Value not defined” dimension values</h3>



<p>Reports may display “<a href="https://matomo.org/faq/reporting-tools/why-does-my-custom-dimension-show-undefined-or-value-not-defined-in-matomo/">undefined” or “Value not defined</a>” as a dimension value.</p>



<p>This has two causes:</p>



<ul class="wp-block-list">
<li>The tracker tried to use a variable that wasn’t defined when&nbsp;<strong>setCustomDimension</strong>&nbsp;was called, so it’s received as “undefined”</li>



<li>The dimension was sent with an empty string, so it displays as “Value not defined”</li>
</ul>



<p>To fix this, teams should set the dimension before the pageview or event is tracked and confirm that the variable returns a real value (unless intentionally left empty).</p>



<h3 class="wp-block-heading">Inconsistent formatting</h3>



<p>Inconsistent formats fragment results. For example, recording &#8220;pro&#8221;, &#8220;Pro&#8221; and &#8220;PRO&#8221; as separate values inflates the number of rows and makes comparisons harder.&nbsp;</p>



<p>Shared naming conventions and validation on the data layer keep values accurate and readable.</p>



<h3 class="wp-block-heading">Implementation validation</h3>



<p>Tag Manager preview mode and browser&nbsp;<strong>Network</strong>&nbsp;tabs can confirm that&nbsp;<strong>dimension{id}</strong>&nbsp;is included in a tracking request. Teams can verify values in the&nbsp;<strong>Visitor Log</strong>&nbsp;before relying on aggregated reports.</p>



<p>Teams should also review dimension values to make sure no personal data is sent and the consent setup blocks tracking where required.</p>



<h2 class="wp-block-heading">Using custom dimensions in Matomo</h2>



<p>Custom dimensions fit neatly into Matomo’s&nbsp;<a href="https://matomo.org/blog/2025/06/privacy-friendly-analytics/">privacy-first approach</a>. The platform combines 100% data ownership with options such as IP anonymisation, cookieless tracking and no data sampling, so added context does not come at the expense of privacy or accuracy.</p>



<p>Matomo treats&nbsp;<a href="https://matomo.org/guide/reporting-tools/custom-dimensions/">custom dimensions</a>&nbsp;as first-class fields in many features. They appear in dedicated reports, can act as rows or columns in&nbsp;<strong>Custom Reports</strong>&nbsp;and can filter or group&nbsp;<strong>Goals</strong>,&nbsp;<strong>Funnels</strong>&nbsp;and&nbsp;<strong>E-commerce</strong>&nbsp;reports. A “Subscription tier” dimension, for example, can break down goal completions by Free, Pro and Enterprise across landing pages, events and revenue, which gives teams a clear view of how each tier behaves.</p>



<p>Business Matomo Cloud plans come with&nbsp;<a href="https://matomo.org/faq/reporting-tools/data-limits-for-custom-dimensions/">15 visit-scope and 15 action-scope dimensions</a>, but Enterprise’s total amount is customisable. On Matomo On-Premise, administrators can extend the default five per scope to around 50 per scope through a&nbsp;<a href="https://matomo.org/faq/how-to/faq_21121/">console command</a>&nbsp;with SSH access.</p>



<h2 class="wp-block-heading">Custom dimensions as a foundation for trusted analytics</h2>



<p>Custom dimensions close the gap between raw metrics and meaningful insight by restoring context to every visit and action.&nbsp;</p>



<p>Instead of isolated page views and bounce rates, teams gain a structured view of how real audiences behave across content, products and technical experiences.&nbsp;</p>



<p>In Matomo, this richer picture rests on a trusted base: accurate data with no sampling, an open-source platform used by more than 1 million websites and features that can be configured for GDPR compliance.&nbsp;</p>



<p>For organisations that value privacy and control, Matomo’s custom dimensions provide a practical path to clearer, more confident decisions.<br /><br />Download Matomo and run it for <a href="https://matomo.org/matomo-on-premise/">free on your own server</a> or <a href="https://matomo.org/start-free-analytics-trial/">start your free Matomo Cloud trial today</a> — no credit card required.</p>



<h2 class="wp-block-heading">FAQ</h2>



<h3 class="wp-block-heading"><strong>What is a custom dimension?</strong></h3>



<p>A custom dimension is a field that stores extra context for a visit or action, such as user role or content category. It appears in dedicated Matomo reports.</p>



<h3 class="wp-block-heading"><strong>When should I use custom dimensions vs. custom variables?</strong></h3>



<p>Custom dimensions are the modern way to track extra metadata in Matomo.&nbsp;<a href="https://matomo.org/faq/general/faq_21117/">Custom variables</a>&nbsp;are deprecated and mainly kept for legacy installations.</p>



<h3 class="wp-block-heading"><strong>What’s the maximum number of custom dimensions allowed in Matomo?</strong></h3>



<p><a href="https://matomo.org/pricing/">Matomo Cloud Business Plan</a>&nbsp;supports 15 custom dimensions per scope (visit and action), so&nbsp;<a href="https://matomo.org/faq/reporting-tools/data-limits-for-custom-dimensions/">30 in total</a>. The Enterprise plan has customisable limits.&nbsp;</p>



<p>On-Premise starts at 5 per scope and&nbsp;<a href="https://matomo.org/faq/how-to/faq_21121/">can be extended</a>&nbsp;to at least 50 per scope using console tools with SSH access.&nbsp;</p>



<h3 class="wp-block-heading"><strong>Can you add custom dimensions retroactively in Matomo?</strong></h3>



<p>Custom dimensions record values from the time tracking is implemented. Earlier visits without that value remain empty in reports.</p>



<h3 class="wp-block-heading"><strong>How do custom dimensions differ from segments in Matomo?</strong></h3>



<p>A custom dimension adds a new field to the dataset, like a membership tier. A segment filters existing data, such as visits from a specific region.</p>



<h3 class="wp-block-heading"><strong>Are Matomo custom dimensions GDPR-compliant?</strong></h3>



<p>Custom dimensions in Matomo can be made GDPR-compliant when configured and governed correctly, following consent, data minimisation, limited retention and anonymisation of personal data where possible. You can learn more in our handy&nbsp;<a href="https://matomo.org/docs/gdpr/">GDPR guide</a>.</p>



<h3 class="wp-block-heading"><strong>Can I use custom dimensions in Matomo’s mobile app analytics?</strong></h3>



<p>Yes. Matomo’s mobile SDKs for Android and iOS support&nbsp;<a href="https://matomo.org/blog/2012/04/how-to-use-piwik-to-track-mobile-apps-activity-clicks-phones-errors-etc/">tracking custom dimensions</a>&nbsp;alongside events, screens and ecommerce actions.</p>
<p>The post <a href="https://matomo.org/blog/2026/03/custom-dimensions/">Custom dimensions: Setup and implementation guide</a> appeared first on <a href="https://matomo.org">Analytics Platform - Matomo</a>.</p>
