---
layout: post
title: Updating Dynamics CRM OnPremise to work with Microsoft Dynamics Marketing 2015
date: 2015-02-04 11:37
author: corey hanson
comments: true
categories: [Articles, Corey Hanson, Dynamics CRM, Uncategorized]
---
<p><a title="Corey Hanson - Click for blog homepage" href="https://microsofttpd.github.io//"><img width="80" height="95" align="right" alt="Corey Hanson - Click for blog homepage" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/corey.jpg" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/corey.jpg" border="0" hspace="10" /></a>If you have Dynamics CRM OnPremise and it is&nbsp;integrated with Dynamics Marketing this post is for you. This post will focus on the steps to you need to perform to allow your integration to continue to work after Dynamics Marketing is upgraded to 2015.</p>
<p>Download the Dynamics Marketing resources: <a href="http://www.microsoft.com/en-us/download/details.aspx?id=43108">http://www.microsoft.com/en-us/download/details.aspx?id=43108</a></p>
<p>Install the Microsoft Dynamics Marketing 17.0.3711 - CRM Connector.msi file on the server you had the previous version installed on.</p>
<p>After the Connector files are installed navigate to C:\Program Files (x86)\Microsoft Dynamics Marketing\Solutions\CRMConnector.&nbsp; Here you will find 2 solution files.</p>
<ul>
<li>DynamicsMarketingConnector_for_CRM2013+CRM2011_managed</li>
<li>DynamicsMarketingConnector_for_CRM2015_managed</li>
</ul>
<p>As you can tell by the names depending on the CRM version you have will determine which solution file you need to import into your Dynamics CRM OnPremise organization.</p>
<p><strong>SOLUTION IMPORT</strong></p>
<ol>
<li>Within Dynamics CRM navigate to Settings-Solutions and click Import</li>
<li>Select the Solution file that matches your version of CRM you have.</li>
<li>Import the file.</li>
</ol>
<p><strong>UNINSTALL CONNECTOR SERVICE</strong>&nbsp;</p>
<p>The previous version of the connector service needs to be uninstalled.&nbsp; To&nbsp;remove the&nbsp;connector service execute this command: <strong>Microsoft.Dynamics.Marketing.DataIntegrationService.exe /uninstall /instance=&lt;instanceName&gt;</strong></p>
<p>&nbsp;instanceName =</p>
<p><strong>INSTALL CONNECTOR SERVICE</strong></p>
<p>Install the connector service with the updated connector service files:</p>
<p>Microsoft.Dynamics.Marketing.DataIntegrationService.exe /install /instance=instanceName /configuration=&ldquo;&lt;configuration file&gt;&rdquo;</p>
<p>More Information&lt;<a href="https://technet.microsoft.com/en-us/library/jj993931(v=crm.6).aspx">https://technet.microsoft.com/en-us/library/jj993931(v=crm.6).aspx</a>&gt;</p>
