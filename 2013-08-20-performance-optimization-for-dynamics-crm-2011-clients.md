---
layout: post
title: Performance Optimization for Dynamics CRM 2011 Clients
date: 2013-08-20 11:20
author: trapti nagar
comments: true
categories: [Address Book Performance, Articles, CRM Outlook Client, CRM Web Client, Dynamics CRM 2011, Offline Synchronization, Optimization, Performance Planning, Techniques, Trapti Nagar, Uncategorized]
---
<p style="text-align:left;"><a title="Trapti Nagar - Click for blog homepage"><img width="80" height="110" align="right" alt="Trapti Nagar - Click for blog homepage" src="https://microsofttpd.github.io/assets/0601.traptin.png" original-url="https://microsofttpd.github.io/assets/0601.traptin.png" border="0" hspace="10" /></a>This blog will give you all possible information about Microsoft Dynamics CRM 2011 Client, factors which affect the performance of your CRM client and the performance improvement techniques specific to client side layer of CRM architecture.</p>
<p>I&nbsp;will also list down the software and hardware resources and their usage to monitor and achieve desired CRM client performance.</p>
<p><strong>How do you decide that you need to improve the performance of your CRM client?</strong></p>
<p>The answer is pretty straightforward, it all depends on &ldquo;<em>How quickly you get the response from the browser and once you receive it how fast you render the objects from the response on the page</em>&rdquo;.</p>
<p><strong>What do you measure in the system to confirm that you need to improve the performance?</strong></p>
<ul>
<li><strong>Time to First Byte:</strong> The time the browser receives the first byte from the server after a request has been made. All your latency issues all your server issues are the culprits here. Long TTFB can mean that the server is experiencing delays processing resources, under heavy load, or doing complex calculations. Time to First Byte, basically depends on amount and efficiency of customizations and if you have some form applications built using Dynamics CRM SDK, that all matters here. Basically it is all about optimizing the traffic, if you can optimize the traffic, you can reduced the traffic and eventually the performance.</li>
<li><strong>Render Start Time:</strong> The start render time is the moment something first displays on the user&#39;s screen. The web page goes from a blank white screen and changes. It doesn&#39;t necessarily have to be content including images and iframes. Before the web page starts to render, browsers must download and parse the objects on the HEAD element, and calculate the initial layout before content can show up on the screen. Optimizing your start render time is mainly a function of server response and optimizing the efficiency of the elements in the HEAD of your HTML documents. There are a number of best practices that can be used to speed up start rendering.</li>
<li><strong>DOM Content Loaded:</strong> The DOMContentLoaded event is triggered when the page&#39;s Document Object Model (DOM) is ready, and when the document has been completely loaded and parsed, without waiting for stylesheets, images, and sub frames to finish loading. You can have a look at this test page to understand this <a href="http://ie.microsoft.com/testdrive/HTML5/DOMContentLoaded/">http://ie.microsoft.com/testdrive/HTML5/DOMContentLoaded/</a></li>
<li><strong>Page Load Time:</strong> The event is triggered when the entire page has loaded. This is moment when the globe or loader in your browser&#39;s title bar stops spinning. The major and most powerful toll for an end user to identify the performance of your Dynamics CRM client .To understand the value and effect of Page Load time you can have a look at one of the very famous user experience and impact study for Page Load Time here: <a href="http://www.webpronews.com/how-page-load-speed-impacts-seo-and-user-experience-2013-04">http://www.webpronews.com/how-page-load-speed-impacts-seo-and-user-experience-2013-04</a><br />Though it is old but holds good even today.</li>
</ul>
<p><strong>The Thumb Rule for Good Performance</strong></p>
<p>After having a look at parameters, there is one solution for major performance problems in for Any Dynamics CRM client, and that is &ldquo;<em>less and Efficient customizations</em>&rdquo;.</p>
<p>The more customization you have for your form, the more time it will take to load and change. Compare a basic form with a customized form. It will help you identify the difference your customization is making on the CRM client. The JavaScript&rsquo;s which we write, may even block your form load. The point is load Extra stuff when you need it and when you do not have any choice.</p>
<p>Ribbon customizations again causes performance issues. With the introduction of contextual ribbon, there is lot of scope for performance to be degraded. Every time the ribbon loads, the xml written behind the ribbon loads. Similarly the little and almost ignorable thing in left side of your form, The Sitemap.</p>
<p>The idea is the lesser stuff&nbsp;you send from server to site and site to server is better for the performance of your client.</p>
<p>Here is a checklist which can help you identify and reduce the issues with your client performance:</p>
<ul>
<li>Optimize Your Form Load Experience.</li>
<li>Keep less fields on the form.</li>
<li>Do not overuse scripts (Avoid OnLoad; Use OnChange since its on demand).</li>
<li>Trim the ribbon appropriately.</li>
<li>Be wary of client side enabled rules.&nbsp;</li>
<li>Use collapsed sections whenever possible.</li>
<li>Use server side show/hide fields.</li>
<li>Use &lsquo;read optimized&rsquo; forms.</li>
<li>Use iFrames carefully, the more you have longer it takes to load.</li>
<li>Use Sub-grids, where necessary as it tend to increase page size quickly.</li>
<li>Manage the complexity and visualizations of dashboards.</li>
</ul>
<p>Other than customizations,</p>
<ul>
<li>Make sure you meet the minimum requirements for Hardware</li>
<li>Power settings can affect performance</li>
<li>Proxy server settings</li>
<li>Configure Internet Explorer for optimal performance: Configuring client-side browser caching and Configuring simultaneous download sessions</li>
<li>Extraneous processes, applications, and add-ins</li>
<li>Security packages and anti-virus applications: Disabling Script sca</li>
<li>Internet Explorer zoom setting</li>
</ul>
<p><strong>The Dynamics CRM Outlook Client</strong></p>
<p>We discussed about Dynamics CRM Web Client in the above sections. Let&rsquo;s now have a look at Dynamics CRM Outlook Client and things we need to keep in mind from performance standpoint. There are several configuration techniques available for optimizing the performance of Microsoft Dynamics CRM for Outlook, which are detailed in the following sections.</p>
<p>These are some recommendations which are also mentioned in the performance whitepaper for dynamics CRM 2011.</p>
<p><strong>Optimizing the Outlook Synchronization Process </strong></p>
<p>Make sure that you configure the filters associated with the Outlook synchronization process too affect the fewest record types and to occur as infrequently as possible without compromising business requirements and to avoid creating duplicate records if key fields match. For more information about the settings and step by step guidance, you can go through this:<br /><a href="http://go.microsoft.com/fwlink/?LLinkID=2155726" target="_blank">http://go.microsoft.com/fwlink/?LLinkID=2155726</a></p>
<p><strong>Optimizing Address Book Performance</strong></p>
<p>To optimize Address Book performance, configure the Address Book to match only against the contacts that are synchronized too Microsoft Dynamics CRM and too retrieve updates as infrequently as possible without compromising business requirements.</p>
<p><strong>Pinning Commonly Used Views </strong></p>
<p>With Microsoft Dynamics CRM for Outlook, users can open tabs to display multiple views of an entity. Users can also &ldquo;pin&rdquo; views so they always display when a user logs in to Outlook. Pinned views, which are stored in cache, respond more quickly than do standard views, so be sure that suggest that users &ldquo;pin&rdquo;&rdquo; the views with which they most commonly interact.</p>
<p>Now here I am going to contradict the above statement a little:</p>
<p>Watch what you pin: as the &ldquo;pin&rdquo; downloads everything on the client that you are using. But it <strong>downloads everything</strong>. So balance it out. People disable MAPI traffic but in certain client it is the only way to go.</p>
<p><strong>Optimizing the Offline Synchronization Process</strong></p>
<p>To optimize the offline synchronization process on computers running Microsoft Dynamics CRM for Outlook with Offline Access, consider the following best practices:</p>
<p>Assign all users roles with the minimum access levels and permissions required to perform a job function to help ensure optimized data synchronization too the offline client.&nbsp;</p>
<p>Avoid &ldquo;Sliding time windows&rdquo; and &ldquo;Parent downloaded=true&rdquo; clauses. Use of this clause often results in the synchronization of unnecessary data, which can degrade the performance of&nbsp; the synchronization&nbsp;</p>
<p>Implement local data filtering for each offline client to ensure that users have offline access only to the data required to perform their job functions. After implementing local data filtering, be sure to remain online and synchronize the data manually. The initial synchronization will be slower than subsequent synchronizations because Microsoft Dynamics CRM must remove records.&nbsp;</p>
<p>Configure offline synchronization to run in the background periodically</p>
<p>For more information about offline synchronization, see the following resources &ldquo;Offline and Online Synchronization in Microsoft Dynamics CRM&rdquo;:</p>
<p><a href="http://www.microsoft.com/en-us/download/details.aspx?id=2737" target="_blank">http://www.microsoft.com/en-us/download/details.aspx?id=2737</a></p>
<p>Frequency of publishing customizations: Maintain the frequency of the publishing process of the latest updates/ customizations you have made to system. Very importantly before UR12 we had to download the metadata every time there are changes or customizations. And after UR 12 it only downloads only the delta. There is a new API which accepts the timestamp and which helps you download the delta.</p>
<p>So make sure&nbsp;you have the UR12 to get benefited by this feature.</p>
<ul>
<li>CRM Outlook client background polling: You might have come across this scenario often. At initial stages, everything is working fine and fast but suddenly everything becomes slow the reason could be there is polling happening at the background which is affecting performance of your outlook client. There are some registry settings that can really help in this situations, I am listing below those settings and what their significance are.</li>
</ul>
<p style="padding-left:30px;"><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/1057.crm2011clientperformance.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/1057.crm2011clientperformance.png"><img alt=" " src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/1057.crm2011clientperformance.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/1057.crm2011clientperformance.png" border="0" /></a></p>
<ul>
<li>
<div>CRM Outlook offline filters: it&rsquo;s a well known fact that the filters hampers the performance, so make sure that you use the filters effectively.</div>
</li>
</ul>
<p><strong>Tools which can be used</strong></p>
<p><strong>CRM latency tool:</strong> Yes, this tool is available for both types of deployments, On-premise and online. It was only available for CRM Online, the CRM Diagnostics tool is released with CRM 2011 Update Rollup 4 for On Premise installations. It runs a couple of tests, measuring latency to the datacenter/server, bandwidth, and performs a few JavaScript performance tests to measure the CPU/browser performance of the machine. You can utilize this tool and improve the performance of your client based on the results you get. For example Microsoft Dynamics CRM 2011 performs best in an environment with less than 150 MS latency.</p>
<p><strong>Fiddler:</strong> This tool is generally used to inspect HTTP traffic as the CRM pages are being loaded. This tool has many features that give you a lot of information and insight into what is happening during the page load. For example you can see number of requests flowing, content of your webpage and scripts of your page.</p>
<p>This covers&nbsp;all the aspects of performance for Dynamics CRM client. In the next blog&nbsp;I will cover SQL server performance optimizations for Dynamics CRM 2011.</p>
<p>I hope this helps.</p>
<p>Until next post!</p>
