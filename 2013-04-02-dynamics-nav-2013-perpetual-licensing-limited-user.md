---
layout: post
title: Dynamics NAV 2013 Perpetual Licensing – Limited User
date: 2013-04-02 09:35
author: sivakumar v
comments: true
categories: [Articles, Dynamics NAV 2013, Full User, Licensing Guide, Limited User, Permissions, Perpetual Licensing, Role Centers, Suvidha Shashikumar, Uncategorized]
---
<p><a title="Suvidha Shashikumar - Click for blog homepage"><img src="https://microsofttpd.github.io/assets/1452.sshashi.jpg" original-url="https://microsofttpd.github.io/assets/1452.sshashi.jpg" alt="Suvidha Shashikumar - Click for blog homepage" width="80" height="95" align="right" border="0" hspace="10" /></a><strong>Note:</strong> Thanks to <a title="Suvidha Shashikumar" href="http://blogs.technet.com/253501/ProfileUrlRedirect.ashx" target="_blank">Suvidha Shashikumar</a> for providing this article.</p>
<p>NAV 2013 is one of the best NAV releases so far and it has a new and simplified licensing model called perpetual licensing. Perpetual Licensing provides a step forward by simplifying how you purchase an ERP solution.</p>
<p>To get a good understanding of NAV 2013 Perpetual licensing model, please read the <a title="ERP licensing guide" href="https://mbs.microsoft.com/partnersource/pricing/announcements/MSDNAVGP2013LicensingGuide" target="_blank">ERP licensing guide</a>.</p>
<p>When it comes to the user access/user types in NAV 2013, there are only 2 types of user licenses:</p>
<ol>
<li>Full User&nbsp;</li>
<li>Limited User&nbsp;</li>
</ol>
<p>As the name specifies, Full user license will have access to all the NAV data (licensed solution functionality) and that&rsquo;s all about it!! But, when it comes to Limited user license, I have come across partners asking following questions:</p>
<ul>
<li>Where can we assign the tables that Limited users can write to?</li>
<li>Do the Limited Users utilize the same Role Centers that are available for the Full Access Users?</li>
<li>Are Limited Users concurrent? How is that controlled?</li>
<li>Why is system allowing the limited user to access everything? Where is the control?</li>
</ul>
<p>Hence, I wanted to write about the Limited user licensing in simple words with few examples to help partners and customers understand this user licensing better.</p>
<p>Limited User licenses provide users full read but limited yet powerful write capabilities to all of the licensed solution functionality through any and all modes of access including the Windows client. The Limited User license is designed to give you a lower-cost alternative for extending ERP to users who only need to perform limited task as defined in the Licensing Guide.</p>
<ul>
<li>The Limited User license is a concurrent license.</li>
<li>A user with this Limited user license will have read access to all the NAV data (licensed solution functionality).</li>
<li>Limited users have write access to</li>
<ul>
<li>Three tables of user&rsquo;s choice except General Ledger (table 17), Permission Set (table number 2000000004), Permission (table number 2000000005) or Access Control (table number 2000000053).</li>
<li>A predefined set of tables given under <strong>Appendix A</strong> in <a title="ERP Licensing Guide" href="https://mbs.microsoft.com/partnersource/pricing/announcements/MSDNAVGP2013LicensingGuide" target="_blank">ERP Licensing Guide</a>.</li>
</ul>
<li>Limited users can access NAV using any client (windows client, web Client, SharePoint client...).</li>
<li>Every limited user can have different set of 3 tables assigned to them to write into along with the tables given under <strong>Appendix A </strong>in <a title="ERP License Guide" href="http://blogs.technet.com/controlpanel/blogs/posteditor.aspx/ERP Licensing Guide" target="_blank">ERP License Guide</a>.</li>
<li>There is no setup available in NAV 2013 where you can specify the 3 additional tables that each limited user can write into. The Limited user licenses are provided purely on trust basis and Microsoft expects partners to make sure that customers use these licenses in the right manner.</li>
</ul>
<p>However, the system restriction for limited users will be enforced in next versions of NAV.</p>
