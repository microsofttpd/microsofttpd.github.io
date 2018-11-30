---
layout: post
title: Connector for Microsoft Dynamics V3 CU 4
date: 2014-12-31 06:59
author: sivakumar v
comments: true
categories: [Articles, Connector, CU4, Dynamics CRM 2015, Dynamics GP 2015, Microsoft Dynamics, Sivakumar Venkataraman, Uncategorized, v3]
---
<p style="text-align:left;"><a title="Sivakumar Venkataraman - Click for blog homepage"><img border="0" hspace="10" alt="Sivakumar Venkataraman - Click for blog homepage" src="https://microsofttpd.github.io/assets/0871.sivav.jpg" width="80" align="right" height="95" /></a>The Connector for Microsoft Dynamics v3 Cumulative Update 4 was released earlier this month. This was an important release which provided the support for integrations into Dynamics CRM 2015. However, it no longer supports Dynamics CRM 2011 or Dynamics CRM 4.0</p>
<p>Some of the interesting features of this release have been listed below.</p>
<ul>
<li>Support for CRM 2015, which requires the updated CRM solutions included in this release (1.0.1603.5) - these CRM solutions include &quot;CRM2015&quot; in their file names</li>
<li>These solutions also provide support for both the summary and information forms for the targeted entities within CRM 2015</li>
<li>New mappings for Microsoft Dynamics AX and CRM Contact integration that handle the new address 3 fields included in CRM 2015 contacts properly.&nbsp; Those changes can be found in the map changes section.</li>
<li>The required Microsoft .NET Framework versions (3.5 and 4.5.2) are checked for during installation.&nbsp; The Microsoft .NET Framework version 4.5.2 can be downloaded here: web installer or offline installer.</li>
<li>The new integration template for creating and integration between Microsoft Dynamics GP and CRM using CRM contacts has been removed</li>
<li>All previous updates for CU 3 have been incorporated into this release</li>
</ul>
<p>To download this release for your Microsoft Dynamics ERP system, go to Customer Source:</p>
<ul>
<li><a href="https://mbs.microsoft.com/customersource/northamerica/AX/downloads/service-packs/mdax_dynamicsconnector" target="_blank">Connector for Microsoft Dynamics AX</a>
<ul>
<li>If you have applied AX 2012 R2 CU 6 or later or if you are targeting AX 2012 R3, an XPO is no longer needed.&nbsp; You can run the ConnectorHelper class that is included in those releases to accomplish the required setup tasks in AX 2012 R2.</li>
<li>Any release after Connector V3 CU2 (3.2.606.2) will support AX 2012 R3</li>
<li>AX 2012 R3 CU 8 is fully supported</li>
<li>The contact integration maps have been updated to include mappings for the new CRM 2015 address 3 fields, see the <a href="http://blogs.msdn.com/b/dynamicsconnector/archive/2014/12/04/connector-for-microsoft-dynamics-v3-cu-4-released.aspx#MapChanges">map changes</a> section for more information on these changes</li>
</ul>
</li>
<li><a href="https://mbs.microsoft.com/customersource/northamerica/GP/downloads/service-packs/mdgp_dynamicsconnector" target="_blank">Connector for Microsoft Dynamics GP</a>
<ul>
<li>All previously supported versions of GP 2010 and GP 2013 are supported</li>
<li>GP 2015 is fully supported</li>
<li>The ability to create an integration from a template using GP customers and CRM contacts has been removed</li>
</ul>
</li>
<li><a href="https://mbs.microsoft.com/customersource/northamerica/NAV/downloads/service-packs/mdnav_dynamicsconnector" target="_blank">Connector for Microsoft Dynamics NAV</a>
<ul>
<li>Microsoft Dynamics NAV 2015 and all previously supported versions of Dynamics NAV are supported with this release</li>
<li>If you are targeting a multi-tenant deployment of Microsoft Dynamics NAV 2013 R2 this release will make that configuration and integration process easier.&nbsp; The steps outlined in <a href="http://blogs.msdn.com/b/dynamicsconnector/archive/2014/04/07/using-a-multi-tenant-deployment-of-microsoft-dynamics-nav-2013-r2-and-connector-for-microsoft-dynamics.aspx">this post</a> are no longer need with this release of Connector for Microsoft Dynamics.</li>
</ul>
</li>
<li><a href="https://mbs.microsoft.com/customersource/northamerica/SL/downloads/service-packs/mdsl_dynamicsconnector" target="_blank">Connector for Microsoft Dynamics SL</a>
<ul>
<li>Previously supported versions of SL continue to be supported by this version</li>
</ul>
</li>
</ul>
<p>Check out the product team blog article in the link below which has more information regarding this release.</p>
<p><a title="http://blogs.msdn.com/b/dynamicsconnector/archive/2014/12/04/connector-for-microsoft-dynamics-v3-cu-4-released.aspx" href="http://blogs.msdn.com/b/dynamicsconnector/archive/2014/12/04/connector-for-microsoft-dynamics-v3-cu-4-released.aspx" target="_blank">http://blogs.msdn.com/b/dynamicsconnector/archive/2014/12/04/connector-for-microsoft-dynamics-v3-cu-4-released.aspx</a></p>
<p>Happy downloading and integrating&hellip;</p>
