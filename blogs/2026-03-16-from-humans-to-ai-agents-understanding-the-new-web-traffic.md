---
title: "From humans to AI agents: understanding the new web traffic"
url: "https://matomo.org/blog/2026/03/humans-agents-understanding-ai-web-traffic/"
date: "Mon, 16 Mar 2026 09:13:52 +0000"
author: "Hannah Kaufhold"
feed_url: "https://matomo.org/blog/feed/"
---
<p>With AI Assistants being an integral part of our private and professional life, many website owners and marketers wonder about how these systems affect traffic.</p>



<p>Often, their organic traffic is flat. But their content keeps showing up in ChatGPT answers. Something is clearly happening, but it’s not reflected in their analytics.</p>



<p>This is the new normal for a lot of teams. AI systems are interacting with websites in fundamentally different ways: some send real visitors, some read your content quietly in the background, and some never send anyone at all.</p>



<p>Understanding the difference is the first step to making sense of what you&#8217;re seeing:</p>



<ol class="wp-block-list" start="1">
<li>The different types of AI systems interacting with websites</li>



<li>The difference between human visitors and automated traffic</li>
</ol>



<p>Once you know this, tools like Matomo can help you measure what’s happening.</p>



<h2 class="wp-block-heading">Understand the different types of AI on the web</h2>



<p>When people talk about “AI traffic,” they often mix very different technologies together.<br />Not all AI systems behave the same way — and they affect your website in different ways.</p>



<p>Understanding these categories already removes much of the confusion around “AI traffic.”</p>



<p>Here are four types you’re likely to encounter.</p>



<h3 class="wp-block-heading">AI chatbots: answer engines for users</h3>



<p>These are tools like:</p>



<ul class="wp-block-list">
<li>ChatGPT</li>



<li>Gemini</li>



<li>Perplexity</li>



<li>Claude</li>



<li>AI-powered search assistants</li>
</ul>



<p>Users type questions and receive answers written by the AI.</p>



<p>Sometimes these answers include links to sources. When a user clicks one of those links, they visit your website.<br />In analytics, this appears as referral traffic.</p>



<p>AI chatbots can also influence traffic when they’re not sending visitors. This happens when the AI provides a full answer inside its interface, and users don’t see the need to click the source link. In some cases, AI chatbots don’t even add a source link to their output. Both cases result in what is known as zero-click behaviour. Your content may still be used as a source, but no visit happens. And while technology can’t track human visits that <em>aren’t</em> happening, there are solutions to track non-human visits, performed by AI crawlers, scrapers and agents.</p>



<h3 class="wp-block-heading">AI crawlers: automated content readers</h3>



<p>AI companies also operate automated programs that read websites. These are called crawlers.</p>



<p>They visit pages automatically to:</p>



<ul class="wp-block-list">
<li>Discover content</li>



<li>Collect information</li>



<li>Update AI systems</li>
</ul>



<p>These visits are not human. They&#8217;re automated requests made by software.</p>



<h3 class="wp-block-heading">AI scrapers: targeted data collectors</h3>



<p>Scrapers are similar to crawlers but more selective. Instead of reading entire websites, they extract specific pieces of content, such as:</p>



<ul class="wp-block-list">
<li>Article text</li>



<li>Headlines</li>



<li>Product details</li>



<li>Structured data</li>
</ul>



<p>This data may be used for training AI models or generating answers. Again, these visits are automated.</p>



<h3 class="wp-block-heading">AI agents: autonomous digital assistants</h3>



<p>A newer category is AI agents. Agents are designed to perform actions on behalf of users.<br />For example, an AI agent might:</p>



<ul class="wp-block-list">
<li>Search multiple websites</li>



<li>Compare products</li>



<li>Fill out forms</li>



<li>Complete tasks online</li>
</ul>



<p>You might ask yourself how AI agents differ from AI chatbots. The difference is that AI chatbots require user prompts for each step, while AI agents can act autonomously once given an initial instruction.</p>



<figure class="wp-block-table is-style-stripes"><table class="has-fixed-layout"><tbody><tr><td><strong>One important detail: AI systems can play multiple roles</strong> <br />The same AI ecosystem can behave in different ways.<br />For example: A chatbot may send human visitors when users click links. The same company may run crawlers that read your content automatically. Some systems may fetch pages in real time while generating answers.<strong> </strong><br /><strong>The key difference for analytics is simple: Who initiated the visit — a human or an automated system?</strong></td></tr></tbody></table></figure>



<h3 class="wp-block-heading">Overview of AI types and what they do</h3>



<figure class="wp-block-table is-style-stripes"><table class="has-fixed-layout"><thead><tr><th><strong>AI type</strong></th><th><strong>What it does</strong></th><th><strong>How it affects traffic</strong></th></tr></thead><tbody><tr><td>Chatbots</td><td>Answer user questions</td><td>May send human visitors or reduce visits</td></tr><tr><td>Crawlers</td><td>Automatically read websites</td><td rowspan="2">Generate automated traffic</td></tr><tr><td>Scrapers</td><td>Extract specific content</td></tr><tr><td>Agents</td><td>Perform tasks online</td><td>May resemble human sessions</td></tr></tbody></table></figure>



<h2 class="wp-block-heading">How AI changes website traffic</h2>



<p>Imagine you run a blog about marketing tools. Over time, you might notice several subtle changes:</p>



<ul class="wp-block-list">
<li>Some informational blog posts receive fewer visits because AI tools answer basic questions directly.</li>



<li>Traffic patterns shift, with different landing pages receiving visits compared with previous months.</li>
</ul>



<p>These different interactions can make traffic patterns look unusual at first glance. But once you understand the different actors, the effects become easier to interpret.</p>



<p>AI influences website traffic in three main ways:</p>



<h3 class="wp-block-heading">AI sending real visitors</h3>



<p>When users click links inside AI chatbots, they arrive on your website like any other visitor.<br />In Matomo, this traffic is visible in the <strong>Acquisition</strong> report, appearing as a dedicated referrer channel type. In a dedicated report, you can even see the metrics for multiple chatbots.</p>



<h3 class="wp-block-heading">AI reducing clicks (zero-click behaviour)</h3>



<p>Sometimes AI tools answer a question completely inside their interface. Users get the information they need without visiting the website. This means your content still influences the answer, but the visit never happens.</p>



<p>As a website owner or marketing team, over time you may notice fewer visits to informational content or changes regarding which landing pages are visited.</p>



<p>While analytics can’t measure visits that never occur, you can monitor visit trends over time, to get an understanding of the shifts that are happening. And keep in mind that zero-click behaviour doesn&#8217;t necessarily mean your content is less relevant. In many cases, it means the content is summarised or referenced by AI systems instead of generating direct visits.</p>



<p>To understand these shifts, it’s useful to monitor changes in landing pages, queries, and referral sources over time.</p>



<h3 class="wp-block-heading">AI generating automated traffic</h3>



<p>Crawlers, scrapers, and some agents generate non-human visits. With popular traffic analysis solutions, these visits often remain untracked and stay invisible. This is where Matomo comes into play. It offers visibility into AI traffic through different report angles.</p>



<h2 class="wp-block-heading">How Matomo helps you stay oriented</h2>



<p>When traffic patterns change, the goal is simple: separate signal from noise. To do this, start with the following quick check:</p>



<h3 class="wp-block-heading">Quick check: how to spot AI-related traffic in Matomo</h3>



<ol class="wp-block-list" start="1">
<li><strong>Look for AI chatbot referrals</strong>:  Go to <strong>Acquisition</strong> → <strong>Referrals</strong> and check whether AI platforms appear as traffic sources.</li>



<li><strong>Monitor landing page trends over time</strong> : If AI tools answer questions directly, visits to informational pages may decline. Compare traffic patterns over time.</li>



<li><strong>Inspect automated AI traffic</strong> : Use <strong>AI Assistant</strong> tracking to see visits and engagement metrics for AI chatbots and AI agents.</li>



<li><strong>Focus on long-term patterns </strong>: AI-related changes usually appear gradually. Comparing months or quarters helps reveal meaningful trends.</li>
</ol>



<p>If you want to explore these signals in more detail, the following sections explain how to investigate them in Matomo.</p>



<p>Keen about testing Matomo’s AI tracking capabilities yourself? <a href="https://matomo.org/start-free-analytics-trial/">Start your 21-day free trial</a> and make the invisible visible!</p>



<h3 class="wp-block-heading">For real visitors coming from AI: identify referral sources</h3>



<p>Look at referral reports in <strong>Acquisition</strong> to see whether new sources, including AI platforms, are sending visitors.</p>



<p>You can analyse things like:</p>



<ul class="wp-block-list">
<li>How this traffic channel performs, compared with other channels like Organic or Social.</li>



<li>How human traffic coming from AI chatbots changes over time and adds to <a href="https://matomo.org/faq/reports/analyse-goal-reports-and-conversion-rates/">goal conversions</a>, and what happens in individual sessions coming from AI chatbots.</li>



<li>What the visitors do after they land on your website, coming from an AI chatbot (e.g., which <a href="https://matomo.org/faq/reports/transitions-analyze-the-previous-and-following-actions-of-your-visitors-for-each-page/">transitions</a> happened).</li>
</ul>



<p>Learn more here: <a href="https://matomo.org/faq/reports/how-to-track-and-analyse-traffic-from-ai-assistants-like-chatgpt-in-matomo-reports/">How to track and analyse traffic from AI Assistants (like ChatGPT) in Matomo reports</a></p>



<p>This helps answer questions like:</p>



<ul class="wp-block-list">
<li>Is this traffic growing over time?</li>



<li>How are visitors from AI tools behaving?</li>



<li>Do they convert differently from traditional search visitors?</li>
</ul>



<h3 class="wp-block-heading">For automated traffic: inspect AI Assistant traffic</h3>



<p>To <a href="https://matomo.org/wp-content/uploads/2026/04/Matomo-AI-Reports-Guide-1.pdf">gain visibility into non-human visits</a> and to be able to act on it, you can use Matomo’s <a href="https://matomo.org/guide/reports/ai-assistants/">AI Assistant tracking</a>. It offers a dedicated report for both <a href="https://matomo.org/faq/reports/ai-chatbots-overview-report/">AI Chatbots</a> and <a href="https://matomo.org/faq/reports/ai-agent-overview-report/">AI Agents</a>. And here’s what they do:</p>



<ul class="wp-block-list">
<li><strong>AI Chatbots</strong>: This report contains three different sub reports, which help you answer the following questions:
<ul class="wp-block-list">
<li>How many requests from AI chatbots does your website get? And how do the chatbots behave during these visits, e.g. what’s the number of unique visited URLs, orphaned pages, or the click-through-rate?</li>



<li>How do metrics like visits and pageviews develop over time?</li>



<li>Which AI chatbots are accessing your website, and which pages are they visiting each?</li>
</ul>
</li>



<li><strong>AI Agents</strong>: This report not only analyses AI traffic but also allows you to compare it to human visits. It offers two sub reports that provide insights regarding the following:
<ul class="wp-block-list">
<li>How many AI Agent visits are there, and how do the AI Agents behave? For example, how many actions are they performing, what’s their average visit duration and bounce rate, and more.</li>



<li>How do these metrics develop over time?</li>
</ul>
</li>
</ul>



<p>With both detailed reports, and the possibility to investigate behaviour over time, teams don’t need to waste time caring about daily fluctuations. Instead, Matomo allows to analyse longer-term patterns, helping teams compare months or quarters to see how traffic sources are shifting.</p>



<h2 class="wp-block-heading">Making sense of the new traffic landscape</h2>



<p>AI is not a single technology. It is an ecosystem of chatbots, crawlers, scrapers, and agents interacting with websites in different ways. Some bring visitors.  Some reduce clicks.  Some generate automated traffic.</p>



<p>In many cases, AI crawlers are discovering and analysing content that may later appear in AI-generated answers.</p>



<p>In that sense, AI systems can be seen as a <strong>new type of audience</strong>: not human readers, but systems that interpret and redistribute information across AI platforms.</p>



<p>That may sound complex, but the basics of analytics remain the same:</p>



<ul class="wp-block-list">
<li>Know your traffic sources.</li>



<li>Separate humans from automation.</li>



<li>Monitor trends over time.</li>



<li>Make decisions based on your own data.</li>
</ul>



<p>One advantage of privacy-first analytics platforms like Matomo is that they provide visibility into automated traffic.</p>



<p>Instead of hiding these signals behind aggressive filtering or opaque modelling, Matomo allows teams to observe how AI systems interact with their websites.</p>



<p>AI hasn&#8217;t made analytics more complicated. It has made the question more precise: are you looking at humans or machines? Once you can answer that, the rest of your analysis stays the same.</p>



<p>Matomo gives you the visibility to ask that question and answer it, whether it&#8217;s a chatbot sending referral traffic or a crawler reading your pages in silence.</p>
<p>The post <a href="https://matomo.org/blog/2026/03/humans-agents-understanding-ai-web-traffic/">From humans to AI agents: understanding the new web traffic</a> appeared first on <a href="https://matomo.org">Analytics Platform - Matomo</a>.</p>
