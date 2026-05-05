---
title: "Everything you need to know about time decay attribution in marketing"
url: "https://matomo.org/blog/2026/02/time-decay-attribution/"
date: "Wed, 18 Feb 2026 21:56:43 +0000"
author: "Joe Maurer"
feed_url: "https://matomo.org/blog/feed/"
---
<p>“<em>Attribution is dead.</em>”</p>



<p>That’s a sentiment we see echoed all the time within marketing circles. It’s tempting to believe this idea when marketers are struggling to prove the value of their efforts. Attribution models like last-click models overvalue the final touchpoint, while first-click models overvalue the early stage of the customer journey.</p>



<p>But if single-touch models distort the picture, it doesn’t mean attribution is dead. You should consider alternatives, such as multi-touch attribution models, that let you see the full picture — at least to&nbsp;<em>some</em>&nbsp;extent.</p>



<p><strong>Time decay attribution</strong>&nbsp;is one such model.</p>



<p>In this article, we’ll explain the concept of time decay attribution, how it works and help you decide if it’s the best attribution model for your business.</p>



<h2 class="wp-block-heading">What is time decay attribution?</h2>



<p><strong>Time decay attribution is a multi-touch model that assigns more credit to touchpoints closer to the conversion.</strong>&nbsp;The more recent the touchpoint, the greater the weight.</p>



<p>Nuclear Physics scientists use a concept called “<em>half-life.</em>” It refers to the time it takes for a substance to reduce to half its amount, and it’s used to assess how long a radioactive substance remains hazardous.</p>



<p>Similarly, in time decay attribution, the model assigns credit to a specific touchpoint based on the half-life you set. The half-life period is considered the most “critical” because it’s closest to the conversion.</p>



<p>For instance, if your half-life is set to seven days, a touchpoint that occurred a week before conversion receives half the credit as one that occurred on the day of conversion. But if it’s more than two weeks, it’ll receive a quarter of the credit.</p>



<h2 class="wp-block-heading">An example of time decay attribution</h2>



<p>The table below shows a hypothetical journey for James, a small-business owner researching loan options over three weeks.</p>



<p>Here’s what the&nbsp;<a href="https://matomo.org/blog/2024/05/customer-journey-analysis/">customer journey</a>&nbsp;looks like:</p>



<ul class="wp-block-list">
<li>Day 1: He starts with a blog post about business financing (21 days out).</li>



<li>Day 8: He receives an email newsletter highlighting competitive rates (14 days out).</li>



<li>Day 15: He visits a product comparison page and bookmarks it (7 days out).</li>



<li>Day 22: He returns directly to the site and submits his application.</li>
</ul>



<figure class="wp-block-table"><table class="has-fixed-layout"><tbody><tr><td><strong>Touchpoint</strong></td><td><strong>Days before conversion</strong></td><td><strong>Relative weight</strong></td><td><strong>Normalised weight</strong></td><td><strong>Attributed value</strong></td></tr><tr><td>Blog post (organic search)</td><td>21</td><td>0.1250</td><td>7.73%</td><td>$773</td></tr><tr><td>Email&nbsp;newsletter</td><td>14</td><td>0.2500</td><td>15.45%</td><td>$1,545</td></tr><tr><td>Product comparison page</td><td>7</td><td>0.5000</td><td>30.90%</td><td>$3,090</td></tr><tr><td>Application page (direct)</td><td>0</td><td>1.0000</td><td>45.92%</td><td>$4,592</td></tr></tbody></table></figure>



<p>Under time decay attribution, the application page and comparison page receive the largest share of credit because they were closest to the decision. But the blog post and email also get credit, but not equally.</p>



<h2 class="wp-block-heading">What are the different types of marketing attribution?</h2>



<p>There are two types of&nbsp;<a href="https://matomo.org/blog/2024/05/customer-journey-analysis/">marketing attribution</a>&nbsp;models: single-touch and multi-touch. The former credits a single channel with the conversion, while the latter credits multiple channels.</p>



<p>Time decay is one of several&nbsp;<a href="https://matomo.org/multi-attribution/">multi-touch attribution</a>&nbsp;models available to marketers.</p>



<figure class="wp-block-table"><table class="has-fixed-layout"><tbody><tr><td><strong>Model</strong></td><td><strong>Type</strong></td><td><strong>Credit distribution</strong></td></tr><tr><td>Last-click</td><td>Single-touch</td><td>100% to final touchpoint</td></tr><tr><td>First-click</td><td>Single-touch</td><td>100% to first touchpoint</td></tr><tr><td>Linear</td><td>Multi-touch</td><td>Equal credit to all touchpoints</td></tr><tr><td>Position-based (U-shaped)</td><td>Multi-touch</td><td>40% first, 40% last, 20% split across the middle</td></tr><tr><td>Time decay</td><td>Multi-touch</td><td>Weighted by recency</td></tr><tr><td>Algorithmic (data-driven)</td><td>Multi-touch</td><td>Weighted by statistical analysis</td></tr></tbody></table></figure>



<p>Apart from time decay attribution, here are the different types of attribution models:</p>



<h3 class="wp-block-heading">1. Last-click attribution</h3>



<figure class="wp-block-table"><table class="has-fixed-layout"><tbody><tr><td><strong>Type</strong></td><td><strong>Single-touch</strong></td></tr><tr><td>Description</td><td>Assigns 100% of credit to the final touchpoint before conversion</td></tr><tr><td>Strengths</td><td>Simple to implement and easy to explain to stakeholders</td></tr><tr><td>Weaknesses</td><td>Ignores every interaction that built awareness and consideration</td></tr><tr><td>Best for</td><td>Short sales cycles focused on direct response campaigns</td></tr></tbody></table></figure>



<p><a href="https://matomo.org/blog/2024/03/last-click-attribution/">Last-click attribution</a>&nbsp;assigns 100% of the credit to the final touchpoint before conversion. If a customer clicked a paid search ad and then converted, that ad gets all the credit — regardless of what they did before.</p>



<p>While it’s a simple model to use and report on, it ignores every interaction that builds awareness and consideration. If you’re a company with long research or sales cycles, you could end up overindexing your investment on one channel.</p>



<h3 class="wp-block-heading">2. First-click attribution</h3>



<figure class="wp-block-table"><table class="has-fixed-layout"><tbody><tr><td><strong>Type</strong></td><td><strong>Single-touch</strong></td></tr><tr><td>Description</td><td>Assigns 100% of credit to the first touchpoint in the journey</td></tr><tr><td>Strengths</td><td>Highlights channels that generate initial awareness</td></tr><tr><td>Weaknesses</td><td>Ignores everything that happened after the first interaction</td></tr><tr><td>Best for</td><td>Brand awareness campaigns and top-of-funnel analysis</td></tr></tbody></table></figure>



<p>First-click attribution does the opposite of last-click attribution. It assigns all credit to the first touchpoint that introduced the customer to your brand.</p>



<p>This model spotlights the channels that generate initial awareness. It’s a useful model if you’re focused on filling the top of the funnel. The trade-off is that it ignores everything that happened afterwards.</p>



<h3 class="wp-block-heading">3. Linear attribution</h3>



<figure class="wp-block-table"><table class="has-fixed-layout"><tbody><tr><td><strong>Type</strong></td><td><strong>Multi-touch</strong></td></tr><tr><td>Description</td><td>Distributes credit equally across all touchpoints</td></tr><tr><td>Strengths</td><td>Recognises every channel’s contribution</td></tr><tr><td>Weaknesses</td><td>Treats a casual blog visit the same as a demo request</td></tr><tr><td>Best for</td><td>Understanding overall channel health in long nurture cycles</td></tr></tbody></table></figure>



<p><a href="https://matomo.org/blog/2024/02/linear-attribution-model/">Linear attribution</a>&nbsp;distributes credit equally across all touchpoints. If there are four interactions, each receives 25%.</p>



<p>In this case, each channel gets equal credit. If you prefer a more balanced view or want to understand which channels you should invest in, the model works well. But it also treats a casual blog visit the same as a demo request.</p>



<h3 class="wp-block-heading">4. Position-based (U-shaped) attribution</h3>



<figure class="wp-block-table"><table class="has-fixed-layout"><tbody><tr><td><strong>Type</strong></td><td><strong>Multi-touch</strong></td></tr><tr><td>Description</td><td>Assigns 40% to the first touch, 40% to the last and 20% across the middle</td></tr><tr><td>Strengths</td><td>Balances awareness and conversion without ignoring mid-funnel activity</td></tr><tr><td>Weaknesses</td><td>Arbitrary split&nbsp;</td></tr><tr><td>Best for</td><td>B2B environments where both lead generation and closing matter</td></tr></tbody></table></figure>



<p><a href="https://matomo.org/blog/2023/03/multi-touch-attribution-models/">Position-based attribution</a>&nbsp;assigns 40% to the first touch, 40% to the last and spreads the remaining 20% across everything in between.</p>



<p>This model balances awareness and conversion but also accounts for the messy middle. The problem is that the 40/40/20 split is arbitrary because your actual customer journey might not follow that pattern.</p>



<h3 class="wp-block-heading">5. Algorithmic (data-driven) attribution</h3>



<figure class="wp-block-table"><table class="has-fixed-layout"><tbody><tr><td><strong>Type</strong></td><td><strong>Multi-touch</strong></td></tr><tr><td>Description</td><td>Uses machine learning to assign credit based on historical conversion patterns</td></tr><tr><td>Strengths</td><td>Adapts to your specific data rather than relying on fixed rules</td></tr><tr><td>Weaknesses</td><td>Requires large data volumes and can become a black box</td></tr><tr><td>Best for</td><td>Enterprises with high traffic and the technical resources to maintain the model</td></tr></tbody></table></figure>



<p>Algorithmic attribution uses machine learning models to assign credit based on historical conversion patterns. Instead of following fixed rules, it adapts to your specific data.</p>



<p>When it works well, it offers the most nuanced view of channel performance. But it requires large data volumes and technical resources to maintain. If you use it, you need to be technically sound to explain why a channel received its score, since it doesn’t give you the most straightforward answer.</p>



<h2 class="wp-block-heading">What are the benefits of time decay attribution?</h2>



<p>Regarding complexity, time decay attribution sits in the middle ground because it’s more sophisticated than single-touch models but doesn’t require the data infrastructure of algorithmic approaches. If you’re in a company with complex sales cycles, this matters.</p>



<p>Unlike single-touch models, you’re considering that other channels were also involved in the conversion. But the actual action could’ve been majorly influenced by the phone call.</p>



<p>That’s why this model can be used for short and long sales cycles. The channel that receives the most credit under the model is the one closest to where the user or customer takes the desired action.</p>



<h3 class="wp-block-heading">Gives a better picture of the customer journey</h3>



<p>The problem with single-touch models is that they force you to pick a winner. Once the channel gets all the credit, the rest get ignored. The reality is that it takes a few touchpoints before you ever get a conversion.&nbsp;</p>



<p>Time decay attribution looks at the entire journey. The only difference is that it weights the credit based on when the user went through the touchpoint. When you’re reporting to stakeholders, it helps them see the whole picture, which builds confidence in your data.</p>



<h3 class="wp-block-heading">Supports long sales cycles</h3>



<p>There are many industries where the sales cycle can last months. According to Focus Digital’s benchmark report, in the financial services industry, it takes<a href="https://focus-digital.co/average-sales-cycle-length-by-industry/" rel="noreferrer noopener" target="_blank">&nbsp;98 days</a>&nbsp;to close a deal. That’s just one example of how complex today’s customer journey is.</p>



<p>Time decay attribution handles these journeys well compared to single-touch models. It looks at all the channels but doesn’t overindex on the earlier touchpoints. As a result, you don’t undervalue top-of-funnel acquisition while analysing your marketing performance and investments.</p>



<figure class="wp-block-image size-large"><img alt="time decay customer journey" class="wp-image-90727" height="586" src="https://matomo.org/wp-content/uploads/2026/02/time-decay-journey-1024x586.png" width="1024" /></figure>



<h2 class="wp-block-heading">Three limitations of time decay attribution</h2>



<p>Ultimately, we also have to acknowledge that no attribution model is perfect. Even time decay attribution can’t give you the most accurate picture, as it’s a hypothetical, rule-based model whose assumptions may not fit every situation.</p>



<p>Here are its limitations:</p>



<h3 class="wp-block-heading">1. It undervalues early interactions</h3>



<p>The way that time decay works creates a structural bias towards top-of-funnel activity.</p>



<p>Even if a prospect found your brand through a LinkedIn post targeting IT directors, that interaction receives the least credit. Even though that post was the very reason they found you in the first place, it’s not necessarily true that the last touchpoint actually encouraged the conversion.</p>



<p>If you’re primarily investing in top-of-funnel activities, it’d be better to use another multi-touch model.</p>



<h3 class="wp-block-heading">2. It’s difficult to find the optimal half-life</h3>



<p>Also, the half-life setting determines how quickly each touchpoint’s credit decays. If it’s set too short, the early touchpoints become almost invisible. But if it’s set too long, you lose the recency weighting that makes the model useful.</p>



<p>Most platforms default to seven days, but it&nbsp;<em>is&nbsp;</em>arbitrary. You’ll need to adjust it based on your sales cycles.&nbsp;</p>



<h3 class="wp-block-heading">3. It’s misaligned with long-term strategy</h3>



<p>Time decay attribution favours&nbsp;<a href="https://matomo.org/faq/reports/analyse-ecommerce-reporting-to-improve-your-sales/#extending-ecommerce-reporting-with-multi-channel-attribution-optional">short-term optimisation</a>. Since it weights the most recent channel most heavily, you might over-optimise that channel. It’s more commonly used to measure the impact of specific marketing campaigns, which is a more short-term approach.</p>



<p>That’s why most companies in the early and late stages<a href="https://www.benchmarkit.ai/_files/ugd/2a084b_a101ec0bf1bc40728cba323928ed1126.pdf">&nbsp;tend to use multi-touch attribution more</a>&nbsp;than growth-stage companies do. Growth-stage companies tend to scale through curated campaigns and ads, while early- and late-stage companies tend to prefer a bird’s-eye view of their marketing efforts.&nbsp;</p>



<figure class="wp-block-image size-full"><img alt="Table showing multi-touch attribution usage increasing as company revenue grows." class="wp-image-90729" height="668" src="https://matomo.org/wp-content/uploads/2026/02/Multi-Touch-Attribution-Model-Relationship-with-Company-Size.png" width="1367" /></figure>



<p class="has-text-align-center"><em>Multi-touch attribution usage grows with company size.</em><br />(<em><a href="https://www.benchmarkit.ai/b2b-marketing-benchmarks" rel="noreferrer noopener" target="_blank">Image source</a>)</em></p>



<h2 class="wp-block-heading">Choosing the right attribution model</h2>



<p>So is attribution dead? Not quite. But it doesn’t make sense to expect a single model to give you all the answers you need. Each model takes a different (and hypothetical) approach based on certain assumptions.</p>



<p><a href="https://matomo.org/faq/multi-channel-conversion-attribution/faq_25500/">Time decay</a>&nbsp;takes you one step closer to using multi-touch attribution to give a more representative view of your customer journey. It doesn’t require a complex data infrastructure like algorithmic attribution, and it captures every touchpoint if possible.</p>



<p>Ask yourself these questions to determine if it fits:</p>



<ul class="wp-block-list">
<li><strong>Does your sales cycle span multiple weeks?</strong>&nbsp;Time decay handles long journeys and gives late-stage touchpoints their due while still crediting earlier interactions.</li>



<li><strong>Are you trying to optimise bottom-of-funnel performance?</strong>&nbsp;The model highlights the channels that were closest to conversion, which is useful when you need to refine late-stage tactics.</li>



<li><strong>Do you need a middle-ground approach?</strong>&nbsp;If last-click feels too blunt and algorithmic attribution feels too complex, time decay gives you an easier middle ground to start with.</li>



<li><strong>Do you need to justify marketing spend to stakeholders?</strong>&nbsp;Time decay provides a clear, explainable logic (recent = more credit) that’s easier to defend in budget conversations compared to algorithmic attribution.</li>



<li><strong>Is your team optimising campaigns in real-time?</strong>&nbsp;If you’re adjusting spend weekly or monthly based on performance, time decay highlights which late-stage tactics are working now.</li>



<li><strong>Are most of your conversions influenced by multiple channels?</strong>&nbsp;If prospects typically interact with three or more touchpoints before converting, you’ll notice that single-touch models mislead you. Time decay is better suited for those situations.</li>



<li><strong>Is your priority conversion efficiency over brand awareness?</strong>&nbsp;Time decay tends to favour bottom-of-funnel optimisation. If top-of-funnel growth is your focus, you may want to pair it with first-click or run both in parallel.</li>
</ul>



<p>Time decay attribution is also very useful when combined with another model. For instance, you can run a first-click model with it to see which channels introduce prospects versus which ones close them.</p>



<p>So, choose the best model depending on your goals, company stage, and sales cycle to get the most representative view of what’s happening.</p>



<p>If you’re ready to experiment with time decay attribution, consider&nbsp;<a href="https://matomo.org/start-free-analytics-trial/">starting a 21-day free trial</a>&nbsp;using&nbsp;<a href="https://matomo.org/matomo-cloud/">Matomo Cloud</a>&nbsp;(no credit card required).</p>
<p>The post <a href="https://matomo.org/blog/2026/02/time-decay-attribution/">Everything you need to know about time decay attribution in marketing</a> appeared first on <a href="https://matomo.org">Analytics Platform - Matomo</a>.</p>
