---
layout: post
title: Mailing Systems in CRM 2011 Demystified - Part 2
date: 2013-05-28 14:59
author: sivakumar v
comments: true
categories: [Aishwarya C Ramachandran, Articles, CRM 2011, CRM for Outlook, CRM Online, Email Router, Exchange Server, Office 365, Outlook, Outlook Client, Uncategorized]
---
<p style="text-align: left;"><a title="Aishwarya C Ramachandran - Click for blog homepage"><img src="https://microsofttpd.github.io/assets/3225.aishram.jpg" original-url="https://microsofttpd.github.io/assets/3225.aishram.jpg" alt="Aishwarya C Ramachandran - Click for blog homepage" width="80" height="95" align="right" border="0" hspace="10" /></a>In the first article of this series, titled, <a title="https://microsofttpd.github.io/archive/2013/05/22/mailing-systems-in-crm-2011-demystified-part-1.aspx" href="https://microsofttpd.github.io/archive/2013/05/22/mailing-systems-in-crm-2011-demystified-part-1.aspx" target="_blank">Mailing Systems in CRM 2011 Demystified - Part 1</a>, <a title="Aishwarya Ramachandran" href="http://blogs.technet.com/258186/ProfileUrlRedirect.ashx" target="_blank">Aishwarya Ramachandran</a> explains how to set up the Outlook Client in CRM 2011. In this article, she explains how to set up CRM Online with Exchange Online and Email Router.</p>
<p><strong>Configuring CRM online + Exchange online + Email Router</strong></p>
<p>Here are some documents available on MSDN that would help throughout the setting up of the email router.</p>
<ul>
<li>Microsoft Dynamics CRM 2011 for E-mail Router Installing Guide for use with Microsoft Dynamics CRM Online</li>
<li>How to configure the Microsoft Dynamics CRM on-premises and Microsoft Dynamics CRM Online E-mail Router in different deployment scenarios</li>
</ul>
<p>The Microsoft Dynamics CRM E-mail Router is a software component that creates an interface between Microsoft Dynamics CRM Online and</p>
<ul>
<li>Microsoft Exchange Server 2003</li>
<li>Microsoft Exchange Server 2007</li>
<li>Microsoft Exchange Server 2010</li>
<li>Microsoft Exchange Online</li>
<li>SMTP, or a&nbsp;</li>
<li>POP3-compliant e-mail server.</li>
</ul>
<p>After the E-mail Router is installed, it transfers e-mail messages to the Microsoft Dynamics CRM system, and it sends outgoing e-mail messages that users created in the Microsoft Dynamics CRM system.</p>
<p>If your organization uses e-mail queues, you must use the E-mail Router. Queues are not supported by using Microsoft Dynamics CRM for Outlook.</p>
<p><strong>Step: 1</strong></p>
<p>Installing the email router for CRM 2011</p>
<p>You can download the email router from this link here : <a title="Microsoft Dynamics CRM 2011 E-mail Router" href="http://www.microsoft.com/en-us/download/details.aspx?id=27818" target="_blank">Microsoft Dynamics CRM 2011 E-mail Router</a></p>
<p>This follows the normal pattern of installation and there would be a window like the one below that requests for confirmation on all the components that should be installed.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3582.1.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3582.1.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3582.1.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3582.1.png" alt="" border="0" /></a></p>
<p><em>Fig: 1 &ndash; Select the components when installing E-mail Router</em></p>
<p>Once the installation is complete a folder called &ldquo;Microsoft Dynamics CRM 2011 E-mail Router&rdquo; gets installed in your system. This folder contains:-</p>
<ul>
<li>
<div>Microsoft Dynamics E-mail Router Configuration Manager</div>
</li>
<li>
<div>Rule Deployment Wizard</div>
</li>
</ul>
<p>After you install the E-mail Router, you must run the E-mail Router Configuration Manager, an application that is installed during Microsoft Dynamics CRM E-mail Router Setup. You can use the E-mail Router Configuration Manager to configure the following:</p>
<ul>
<li>
<div><strong>One or more incoming profiles </strong>: An incoming profile contains the information about the e-mail systems that will be used to process incoming e-mail messages.</div>
</li>
<li>
<div><strong>One or more outgoing profiles</strong> : An outgoing profile contains the information about the e-mail systems that will be used to process outgoing e-mail messages.</div>
</li>
<li>
<div><strong>One or more deployments</strong> : The Deployments area contains information about the Microsoft Dynamics CRM deployment and maps to an incoming and outgoing profile.</div>
</li>
<li>
<div><strong>Users, queues, and forward mailboxes</strong>&nbsp;: This area contains information about each user that will use the E-mail Router for e-mail tracking. You can also configure e-mail routing for queues and define a forward mailbox.</div>
</li>
</ul>
<p>The Rule Deployment Wizard is used to configure the forward mailbox, which would be explained in the next part of this blog.</p>
<p><strong>Step 2:</strong>&nbsp;&nbsp;</p>
<p>Ensure that the user is configured to utilize &lsquo;E-mail Router&rsquo;</p>
<p>To configure you should navigate to:- <em>Settings &gt;&gt; Administration &gt;&gt; Users &gt;&gt; *Open the user&rsquo;s record&rsquo; &gt;&gt; Scroll to the middle and look for &ldquo;Email access type &ndash; Incoming&rdquo;</em></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/5023.2.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/5023.2.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/5023.2.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/5023.2.png" alt="" border="0" /></a>&nbsp;</p>
<p><em>Fig: 2 - A section of a user record in CRM online</em></p>
<p>The email address given in the user record must be approved by the CRM Administrator.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8726.3.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8726.3.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8726.3.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8726.3.png" alt="" border="0" /></a></p>
<p><em>Fig: 3 - Approving a user&rsquo;s email ID from within the users record</em></p>
<p><strong>Step 3:</strong>&nbsp;</p>
<p>Open the E-mail router Configuration Wizard and configure Outgoing Profile for Exchange online</p>
<p>To configure an <strong>Outgoing profile</strong> for <strong>Exchange Online</strong>:</p>
<p>1. Start the<strong> E-mail Router Configuration Manager</strong> by pointing to <strong>Start</strong> and then click on<strong> All Programs</strong>, click on Microsoft Dynamics CRM 2011 E-mail Router, click on <strong>Microsoft Dynamics CRM E-mail Router Configuration</strong></p>
<p>2. Click <strong>Configuration Profiles</strong> and then click <strong>New</strong></p>
<p>3. In the <strong>E-mail Router Configuration Profile</strong> dialog box, type a profile name. For example, type OutgoingExchangeOnlineE-mail</p>
<p>4. For Direction, select <strong>Outgoing</strong></p>
<p>5. For <strong>E-mail Server Type</strong>, select <strong>Exchange Online</strong>. The value for Protocol automatically changes to <strong>Exchange Web Services</strong> and the value for Authentication Type automatically changes to <strong>Clear Text</strong>.</p>
<p><strong>Important</strong>: Clear Text is secure because SSL is required when Exchange Online is the e-mail server.</p>
<p>6. In the <strong>Server field</strong>, enter the complete URL for the outgoing e-mail server. Use the <strong>Exchange Web Services (EWS) URL format</strong> (EWS/exchange.asmx), as shown in the following example:</p>
<p><a href="https://podxxxxx.outlook.com/EWS/Exchange.asmx">https://podxxxxx.outlook.com/EWS/Exchange.asmx</a></p>
<p>You can find the value of &lsquo;xxxx&rsquo; in the URL when you go to the &lsquo;Outlook&rsquo; tab of any user in O365.&nbsp;</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7534.4.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7534.4.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7534.4.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7534.4.png" alt="" border="0" /></a></p>
<p><em>Fig: 4 - CRM System Users Outlook URL</em></p>
<p>7.&nbsp; Go ahead and create a profile like the one I have created in my environment</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/1464.5.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/1464.5.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/1464.5.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/1464.5.png" alt="" border="0" /></a></p>
<p><em>Fig: 5 - Creating an Outgoing Profile</em></p>
<p><strong>Tip:</strong></p>
<p>Instead of typing a URL, you can select the Use Autodiscover option to use the Autodiscover service as the way to obtain the Exchange Web Services URL.</p>
<p><strong>Note:</strong> If you select Administrator as the user type, you must select either <strong>Delegate Access</strong> or <strong>Send As permission</strong> as the access type. <strong>Delegate Access</strong> causes e-mail to be sent as "<strong>Send on behalf of</strong>" messages. <strong>Send As</strong> permission causes e-mail to be sent as "<strong>Send As</strong>" messages.&nbsp;</p>
<p><strong>Critical: </strong>The credentials specified in the outgoing profile <strong>must have "PublishingEditor"</strong> <strong>permissions (Delegate Access) or Send As permissions</strong> on the Exchange Online mailboxes that need to be accessed. <strong>Exchange Online administrators and users do not have this by default</strong>. To add delegate permissions, Full Access</p>
<p>permissions must be granted to the user in the Outgoing Profile. To add Send As permissions, Send As permissions must be granted to the user in the Outgoing Profile. These permissions <strong>must be added via Powershell</strong>.</p>
<p><a title="To Connect Windows Powershell to the Exchange Online Service" href="http://help.outlook.com/en-us/140/cc952755.aspx" target="_blank">To Connect Windows Powershell to the Exchange Online Service</a></p>
<p><a title="To give an Administrator Full Access Permissions to a Mailbox" href="http://help.outlook.com/140/gg709759.aspx" target="_blank">To give an Administrator Full Access Permissions to a Mailbox</a></p>
<p><a title="To Give a User Send as Permissions" href="http://help.outlook.com/en-us/140/ff852815.aspx" target="_blank">To Give a User Send as Permissions</a></p>
<p>9. Click on Ok</p>
<p>10. Within the E-mail Router Configuration Manager, click on Publish</p>
<p><strong>Step 4: </strong></p>
<p>Open the E-mail router Configuration Wizard and configure Incoming Profile for Exchange online</p>
<p>To configure an <strong>Incoming Profile</strong> with <strong>Exchange Online</strong>:</p>
<p>1. Start the <strong>E-mail Router Configuration Manager</strong> by clicking on <strong>Start</strong> and then click on <strong>All Programs</strong>, click on Microsoft Dynamics CRM 2011 E-mail Router, click on <strong>Microsoft Dynamics CRM E-mail Router Configuration</strong>.</p>
<p>2. Click <strong>Configuration Profiles</strong> and then click <strong>New</strong></p>
<p>3. In the E-mail Router Configuration Profile dialog box, type a <strong>profile na</strong>me. For example, type Incoming E-mail</p>
<p>4. For <strong>Direction</strong>, select <strong>Incoming</strong></p>
<p>5. For <strong>E-mail Server Type</strong>, select <strong>Exchange Online</strong>. The value for Protocol automatically changes to <strong>Exchange Web Services</strong> and the value for Authentication Type automatically changes to <strong>Clear Text</strong>.</p>
<p><strong>Important: </strong>Clear Text is secure because SSL is required when Exchange Online is the e-mail server.</p>
<p>6. In the <strong>Server field</strong>, enter the complete URL for the<strong> incoming e-mail server</strong>. Use the <strong>Exchange Web Services (EWS) URL format</strong> (EWS/exchange.asmx), as shown in the following example:</p>
<p><a href="https://podxxxxx.outlook.com/EWS/Exchange.asmx">https://podxxxxx.outlook.com/EWS/Exchange.asmx</a><br />You can find the value of &lsquo;xxxx&rsquo; in the URL when you go to the &lsquo;Outlook&rsquo; tab of this user in O365.&nbsp;</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4201.6.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4201.6.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4201.6.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4201.6.png" alt="" border="0" /></a></p>
<p><em>Fig:&nbsp;6 - CRM System Users Outlook URL</em></p>
<p><strong>Tip: </strong>Instead of typing a URL, you can select the Use Autodiscover option to use the Autodiscover service as the way to obtain the Exchange Web Services URL.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2043.7.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2043.7.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2043.7.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2043.7.png" alt="" border="0" /></a></p>
<p><em>Fig:&nbsp;7 - Creating an Incoming Profile</em></p>
<p><strong>Step 5:</strong></p>
<p>Now that the incoming and outgoing profile have been set the next step is to setup the deployment in E-mail configuration wizard</p>
<ul>
<li>
<div>If you are connecting to Microsoft Dynamics CRM Online and your organization uses Microsoft Office 365, enter:</div>
</li>
<ul>
<li>
<div><a href="https://disco.crm.dynamics.com/<OrganizationName">https://disco.crm.dynamics.com/&lt;OrganizationName</a>&gt; where Organization Name is a placeholder for the actual ID of your organization.</div>
</li>
</ul>
<li>
<div>This information can be found by navigating to</div>
</li>
<ul>
<li>
<div><em>Settings &gt;&gt; Customizations &gt;&gt; Developer Resources</em></div>
</li>
</ul>
</ul>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4478.8.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4478.8.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4478.8.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4478.8.png" alt="" border="0" /></a></p>
<p><em>Fig:&nbsp;8 - Creating a new deployment</em></p>
<p>Don&rsquo;t forget to &lsquo;Publish&rsquo; your changes prior to moving to Users, Queues and Forward Mailboxes</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/5808.9.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/5808.9.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/5808.9.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/5808.9.png" alt="" border="0" /></a></p>
<p><em>Fig:&nbsp;9 - The dialog that would be seen when &lsquo;Publish&rsquo; is created in the E-mail Router Configuration Wizard</em></p>
<p><strong>Step 6: </strong></p>
<p>Once the Outgoing Profile, the Incoming profile and the Deployments has been configured the next step is to</p>
<ol>
<li>
<div>Load data</div>
</li>
<li>
<div>Test access</div>
</li>
</ol>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2630.10.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2630.10.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2630.10.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2630.10.png" alt="" border="0" /></a></p>
<p><em>Fig:&nbsp;10 - The discovery web Service URL get automatically copied at the last section of the wizard</em></p>
<p>Once data is loaded the users in your CRM system that has been configured to utilize the email router as its mailing system would be seen here.&nbsp;</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/0333.11.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/0333.11.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/0333.11.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/0333.11.png" alt="" border="0" /></a></p>
<p><em>Fig: 11 - All the users that use the email router would load once &lsquo;Load Data&rsquo; is selected</em></p>
<p>Once the Incoming and Outgoing status of all your users succeeds, you should not have any more issues&nbsp;</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3757.12.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3757.12.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3757.12.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3757.12.png" alt="" border="0" /></a></p>
<p><em>Fig: 12 - The window that would be seen when incoming and outgoing status succeeds</em></p>
<p>Now keeping the e-mail router open go ahead and try sending an email from your CRM system and you should be able to get it working!!</p>
<p>Hope this helps.</p>
<p>Until next post!</p>
