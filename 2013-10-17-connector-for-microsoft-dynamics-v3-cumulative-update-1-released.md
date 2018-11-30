---
layout: post
title: Connector for Microsoft Dynamics V3 Cumulative Update 1 – Released!
date: 2013-10-17 10:39
author: sivakumar v
comments: true
categories: [Articles, Connector, Connector for Microsoft Dynamics, CRM Connector, Dynamics AX, Dynamics CRM, Dynamics GP, Dynamics NAV, Dynamics SL, Enhancements, Microsoft Dynamics NAV 2013, New Features, Sivakumar Venkataraman, Uncategorized, Version support]
---
<p style="text-align: left;"><a title="Sivakumar Venkataraman - Click for blog homepage"><img src="https://microsofttpd.github.io/assets/0871.sivav.jpg" alt="Sivakumar Venkataraman - Click for blog homepage" width="80" height="95" align="right" border="0" hspace="10" /></a>Performance improvements and key suggestions on Connector V3 deployments are the primary new features in Connector for Microsoft Dynamics V3 CU1 (3.1.116.2), which was posted today for download.</p>
<p>Additional new features with this release include:</p>
<ul>
<li>Overall performance improvement in the Connector V3 service</li>
<li>Overall performance improvement in Connector's log</li>
<li>Performance improvement&nbsp; in the Microsoft Dynamics CRM 2011 adapter</li>
<li>When you reset the Retry feature, it will now run immediately</li>
</ul>
<p>To download this release for your Microsoft Dynamics ERP system, go to CustomerSource:</p>
<ul>
<li><a href="https://mbs.microsoft.com/customersource/downloads/servicepacks/mdax_dynamicsconnector.htm" target="_blank">Connector for Microsoft Dynamics AX</a>
<ul>
<li>If you have applied Microsoft Dynamics AX 2012 R2 CU 6 or later, an XPO is no longer needed.&nbsp; You can run the ConnectorHelper class that is included in this update to accomplish the required setup tasks in Microsoft Dynamics AX.</li>
</ul>
</li>
<li><a href="https://mbs.microsoft.com/customersource/downloads/servicepacks/mdgp_dynamicsconnector.htm" target="_blank">Connector for Microsoft Dynamics GP</a>
<ul>
<li>All previously supported versions of Microsoft Dynamics GP 2010 and GP 2013 are supported as either new or existing integrations</li>
</ul>
</li>
<li><a href="https://mbs.microsoft.com/customersource/downloads/servicepacks/mdnav_dynamicsconnector.htm" target="_blank">Connector for Microsoft Dynamics NAV</a>
<ul>
<li>Microsoft Dynamics NAV 2013 R2 is supported with this release, however this release is not required for an integration to Microsoft Dynamics NAV.&nbsp; Any release after Connector V2 RU1 (2.1.29.1) will support Microsoft Dynamics NAV 2013&nbsp; R2.</li>
</ul>
</li>
<li><a href="https://mbs.microsoft.com/customersource/downloads/servicepacks/mdsl_dynamicsconnector.htm" target="_blank">Connector for Microsoft Dynamics SL</a></li>
</ul>
<p>Would you like to know more?&nbsp; Check out the User Guide for your ERP system and begin your installation preparation. I know, I know; reading documentation can be arduous. But you know what they say: an ounce of prevention is worth a pound of cure. So read the provided documentation to avoid the common mistakes and save yourself the support call.&nbsp; The user guides for all of the ERPs have been updated for this release and all include a V3 upgrade sections that you should be familiar with <em>before</em> upgrading your existing integrations.&nbsp; All of the known issues documents have been updated as well so please have a look at those too, they can all be found on the Connector for Microsoft Dynamics download pages.</p>
<ul>
<li><a href="http://www.microsoft.com/download/en/details.aspx?id=10381" target="_blank">Connector for Microsoft Dynamics User Guides</a></li>
</ul>
<p>Note: This release includes an update to the MSDI database that will mean any custom objects you have added to the database will be dropped, however this update will greatly improve the performance of the overall Connector system.</p>
