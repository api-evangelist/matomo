---
title: "CNIL compliance in Matomo is now a single click. Here’s what that changes."
url: "https://matomo.org/blog/2026/04/gpdr-cnil-compliance-single-click-feature-new/"
date: "Wed, 08 Apr 2026 15:46:39 +0000"
author: "Alex Carmona"
feed_url: "https://matomo.org/blog/feed/"
---
<p>If you run analytics for a French audience, you might already know about the CNIL consent exemption. And you know that privacy requirements can slow everything down.</p>



<p>Getting GDPR-compliant analytics for France used to mean working through a detailed checklist, tweaking buried settings, and hoping you hadn&#8217;t missed anything.</p>



<p><strong>Matomo&#8217;s new 1-Click CNIL compliance feature handles that automatically</strong>, so you can focus on your data, not your configuration.</p>



<p>The new feature helps you assess your current setup against CNIL consent exemption conditions, apply supported settings <strong>in one click</strong>, and see clearly what still needs your attention.</p>



<p class="has-base-2-background-color has-background"><em>Reminder: you need to comply with CNIL requirements <strong>as soon as your audience includes people in France</strong>, even if your organisation isn&#8217;t French.</em></p>



<div class="wp-block-spacer" style="height: 30px;"></div>



<h2 class="wp-block-heading" id="Why-this-matters">Why this matters</h2>



<p>For many teams, the hard part isn&#8217;t choosing a privacy-first analytics platform. The hard part is configuring it correctly, documenting it clearly, and reducing the back and forth between marketing, implementation, and compliance team.</p>



<p>That changes with today&#8217;s release. Instead of reviewing settings one by one across different parts of Matomo, the 1-Click CNIL compliance feature reduces that friction at every stage:</p>



<ul class="wp-block-list">
<li>Fewer back-and-forths between marketing, development and privacy teams during setup.</li>



<li>Less risk of misconfiguration, because the platform enforces the required settings rather than relying on a checklist.</li>



<li>Easier to review for stakeholders and DPOs, with a clear compliance status per site and a self-assessment document built in.</li>



<li>Faster to deploy across multiple sites, without repeating the same manual process each time.</li>
</ul>



<p>This is especially useful for teams that need a faster and clearer path to a CNIL-aligned setup, without relying on scattered documentation or repeated manual reviews.</p>



<p>It&#8217;s also relevant <strong>if you&#8217;re evaluating Matomo against alternatives</strong>. <a href="https://matomo.org/faq/how-to/how-do-i-configure-matomo-without-tracking-consent-for-french-visitors-cnil-exemption/" rel="noreferrer noopener" target="_blank">CNIL compliance</a> has historically required external setup support or a specialist. It no longer does.</p>



<div class="wp-block-spacer" style="height: 50px;"></div>



<h2 class="wp-block-heading" id="What-1-Click-CNIL-compliance-does"><strong>What 1-Click CNIL compliance does</strong></h2>



<p>The feature lives at Administration > Privacy > Compliance. Select a site from the dropdown and Matomo runs a full assessment of your current configuration against <a href="https://matomo.org/faq/how-to/how-do-i-configure-matomo-without-tracking-consent-for-french-visitors-cnil-exemption/" rel="noreferrer noopener" target="_blank">CNIL requirements</a>.</p>



<p>Each setting is assigned one of three statuses:</p>



<ul class="wp-block-list">
<li><strong>Compliant</strong>: your current configuration meets the requirement.</li>



<li><strong>Non-compliant:</strong> the setting needs to be changed, and Matomo can apply it automatically.</li>



<li><strong>Unknown:</strong> Matomo cannot verify this from within the platform. It requires a manual step on your end.</li>
</ul>



<div class="wp-block-spacer" style="height: 30px;"></div>



<figure class="wp-block-image size-large"><img alt="1 click cnil demo Matomo" class="wp-image-92284" height="1024" src="https://matomo.org/wp-content/uploads/2026/04/1-click-cnil-demo-Matomo-1006x1024.webp" width="1006" /></figure>



<div class="wp-block-spacer" style="height: 30px;"></div>



<p>Once you&#8217;ve reviewed the results, enable &#8220;Enforce compliance where possible&#8221; and click Save. <strong>Matomo applies all supported settings in one go</strong>. The compliance page also links directly to the knowledge base and to <a href="https://matomo.org/wp-content/uploads/2026/04/CNIL-Consent-Exemption-Self-Assessment-Table.pdf" rel="noreferrer noopener" target="_blank">the self-assessment document</a>, which CNIL now requires analytics providers to make available to their customers.</p>



<div class="wp-block-spacer" style="height: 50px;"></div>



<h2 class="wp-block-heading" id="What-changes-when-you-enable-it"><strong>What changes when you enable it</strong></h2>



<p>When CNIL mode is enforced, Matomo applies a restricted configuration for the selected site or app. That can include:</p>



<figure class="wp-block-table"><table class="has-fixed-layout"><tbody><tr><th class="has-text-align-left">Data collection and anonymisation</th><th class="has-text-align-left">Individual-level data</th><th class="has-text-align-left">Reporting and retention</th></tr><tr><td class="has-text-align-left">&#8211; Visitors&#8217; IP addresses are anonymised, with the mask set to two bytes.<br />&#8211; Only first-party cookies are used. Cross-domain tracking is disabled.<br />&#8211; Campaign parameters and advertising identifiers are stripped at ingestion and not stored.<br />&#8211; Ecommerce tracking is set to restricted mode. Order IDs are anonymised, and identifying segments are disabled. </td><td class="has-text-align-left">&#8211; Visits Log and Visitor Profiles are disabled. Only aggregated, anonymous statistics remain available.<br />&#8211; Heatmaps and Session Recordings are disabled.<br />&#8211; A/B Testing is disabled. Note that enabling compliance mode permanently deletes all existing experiments.</td><td class="has-text-align-left">&#8211; Segmented data is rounded to the nearest ten to prevent singling out individuals.<br />&#8211; The data retention period is automatically set to 180 days.</td></tr></tbody></table></figure>



<p>This is what makes the feature useful in practice. It does not just tell you what the requirements are. It helps you <strong>apply</strong> the supported settings in one place and makes the remaining gaps visible.</p>



<div class="wp-block-spacer" style="height: 50px;"></div>



<h2 class="wp-block-heading" id="What-still-requires-a-manual-step"><strong>What still requires a manual step</strong></h2>



<p>This is worth reading before you enable the feature:</p>



<p>The <a href="https://matomo.org/faq/general/faq_20000/" rel="noreferrer noopener" target="_blank">opt-out mechanism</a> is not configured automatically. CNIL requires that visitors can object to audience measurement, and this must be embedded in your privacy policy as an iframe or link. The compliance page flags this with an &#8220;Unknown&#8221; status. The configuration guide walks you through the setup.</p>



<p>Any settings marked <strong>Unknown</strong> in your assessment also need manual review. Matomo cannot verify them from within the platform, and CNIL compliance cannot be confirmed until they are addressed.</p>



<p>Custom goals and events you create must stay within the three categories of events permitted by CNIL: presence on a page, use of a feature, and page performance statistics. Anything outside that scope falls outside the exemption.</p>



<p>Finally, this feature supports the compliance process. It does <strong>not</strong> replace legal review. If you operate in a regulated sector or manage compliance across multiple jurisdictions, your legal or privacy team should validate your configuration.</p>



<div class="wp-block-spacer" style="height: 50px;"></div>



<h2 class="wp-block-heading" id="Where-to-start"><strong>Where to start</strong></h2>



<p>It’s already available for superusers in Privacy > Compliance. The feature is live now on Matomo Cloud and available on Matomo On-Premise with version 5.9.0.</p>



<p>If you want to use Matomo in a way that may qualify for CNIL consent exemption when properly configured, start here:</p>



<ul class="wp-block-list">
<li>go to <strong>Administration > Privacy > Compliance</strong></li>



<li>select the relevant site</li>



<li>review the assessment results</li>



<li>enable <strong>Enforce compliance where possible</strong></li>



<li>complete the remaining manual steps, especially opt-out setup</li>



<li>review the detailed self-assessment and knowledge base guidance for the full scope and restrictions </li>
</ul>



<div class="wp-block-spacer" style="height: 30px;"></div>



<p>The full configuration guide and self-assessment document are available in our knowledge base:</p>



<ul class="wp-block-list">
<li><a href="https://matomo.org/wp-content/uploads/2026/04/Configure-Matomo-Analytics-for-CNIL-exemption-User-Guide.pdf" rel="noreferrer noopener" target="_blank">our English configuration guide</a></li>



<li><a href="https://matomo.org/wp-content/uploads/2026/04/Configurer-Matomo-pour-la-CNIL-FR.pdf" rel="noreferrer noopener" target="_blank">our French configuration guide</a></li>



<li><a href="https://matomo.org/faq/how-to/how-do-i-configure-matomo-without-tracking-consent-for-french-visitors-cnil-exemption/" rel="noreferrer noopener" target="_blank">our technical documentation for 1-Click CNIL Compliance</a>, with <a href="https://matomo.org/wp-content/uploads/2026/04/CNIL-Consent-Exemption-Self-Assessment-Table.pdf" rel="noreferrer noopener" target="_blank">the CNIL self-assessment</a></li>



<li><a href="https://matomo.org/faq/general/faq_20000/" rel="noreferrer noopener" target="_blank">our opt-out setup guide</a></li>
</ul>



<p>These resources explain the detailed conditions, scope limitations, and remaining manual actions required for your setup.</p>



<div class="wp-block-spacer" style="height: 50px;"></div>



<h2 class="wp-block-heading" id="Analytics-that-are-easier-to-review,-easier-to-configure,-and-easier-to-trust"><strong>Analytics that are easier to review, easier to configure, and easier to trust</strong></h2>



<p>Privacy-conscious analytics should not require a maze of manual checks.</p>



<p>With 1-Click CNIL Compliance, Matomo gives your team a more direct way to assess its setup, apply supported CNIL-aligned settings, and document what still needs to be done.</p>



<p>It is a practical step toward analytics that are easier to configure, easier to review internally, and easier to operationalise across teams.</p>



<p>Learn more about this new feature here: <a href="https://matomo.org/faq/how-to/how-do-i-configure-matomo-without-tracking-consent-for-french-visitors-cnil-exemption/" rel="noreferrer noopener" target="_blank">How do I configure Matomo without tracking consent for French visitors (CNIL exemption)?</a></p>
<p>The post <a href="https://matomo.org/blog/2026/04/gpdr-cnil-compliance-single-click-feature-new/">CNIL compliance in Matomo is now a single click. Here’s what that changes.</a> appeared first on <a href="https://matomo.org">Analytics Platform - Matomo</a>.</p>
