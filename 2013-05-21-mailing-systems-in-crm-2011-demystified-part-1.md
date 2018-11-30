---
layout: post
title: Mailing Systems in CRM 2011 Demystified - Part 1
date: 2013-05-21 13:07
author: sivakumar v
comments: true
categories: [Aishwarya C Ramachandran, Articles, CRM 2011, CRM for Outlook, CRM Online, Email Router, Exchange Server, Office 365, Outlook, Outlook Client, Uncategorized]
---
<p style="text-align: left;"><a title="Aishwarya C Ramachandran - Click for blog homepage"><img src="https://microsofttpd.github.io/assets/3225.aishram.jpg" original-url="https://microsofttpd.github.io/assets/3225.aishram.jpg" alt="Aishwarya C Ramachandran - Click for blog homepage" width="80" height="95" align="right" border="0" hspace="10" /></a><strong>Note:</strong> Credits to <a title="Aishwarya Ramachandran" href="http://blogs.technet.com/258186/ProfileUrlRedirect.ashx" target="_blank">Aishwarya Ramachandran</a> for this series of articles.</p>
<p>This is the first part of the series of articles that we are planning to publish on <strong>Mailing Systems in CRM 2011 Demystified</strong>.&nbsp;&nbsp;</p>
<p>CRM online does not have a mailing system of its own.</p>
<p>There are 3 options for sending and receiving Emails with Dynamics CRM Online:</p>
<ol>
<li>Use the Outlook Client directly.</li>
<li>Use the Outlook Client started in the background and sending mails from the CRM Web-Client</li>
<li>By using only the CRM Web-Client in conjunction with the Email Router</li>
</ol>
<p>There are 2 possibilities to connect Dynamics CRM Online with Exchange Online:</p>
<ol>
<li>By using the Outlook Client</li>
<li>By using the Email Router</li>
</ol>
<p><strong>Configuring CRM online + Exchange online + Outlook Client</strong></p>
<p><strong>Step:&nbsp;1</strong> <br />Ensure that the user is configured to utilize &lsquo;Microsoft Dynamics CRM for Outlook&rsquo;</p>
<p>To configure you should navigate to Settings &gt;&gt; Administration &gt;&gt; Users &gt;&gt; *Open the user&rsquo;s record&rsquo; &gt;&gt; Scroll to the middle and look for &ldquo;Email access type &ndash; Incoming&rdquo;</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3223.1.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3223.1.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3223.1.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3223.1.png" alt="" border="0" /></a></p>
<p><em>Fig: 1 - A section of a user record in CRM online</em></p>
<p><strong>Step: 2</strong>&nbsp;</p>
<p>The email address given in the user record must be approved by the CRM Administrator.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7002.2.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7002.2.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7002.2.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7002.2.png" alt="" border="0" /></a></p>
<p><em>Fig: 2 - Approving a user&rsquo;s email ID from within the users record</em></p>
<p><strong>Step 3:</strong></p>
<p>There are 2 methods to view this mailbox in outlook</p>
<ul>
<li>
<div>Create a new profile in Outlook</div>
</li>
<li>
<div>Add a new account in Outlook</div>
</li>
</ul>
<p><span style="text-decoration: underline;"><strong>Create a new profile</strong></span></p>
<p><em>Control Panel &gt;&gt; Mail &gt;&gt; Show profile</em></p>
<p>After adding a profile you can prompt for outlook to request which profile you would like to open.</p>
<p><span style="text-decoration: underline;"><strong>Add a new account in Outlook</strong></span></p>
<p><em>File &gt;&gt; Add new account</em></p>
<p>Once you add your O365 address and give in your password, a mail box would be created.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3755.3.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3755.3.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3755.3.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3755.3.png" alt="" border="0" /></a></p>
<p><em>Fig: 3 - Adding a new account to Outlook 2010 client</em></p>
<p>&nbsp;</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4478.4.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4478.4.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4478.4.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4478.4.png" alt="" border="0" /></a></p>
<p><em>Fig: 4 - The outlook client authenticates the credentials and connects to Exchange online</em></p>
<p><strong>Step 4:</strong></p>
<p>Download the Microsoft Dynamics CRM 2011 for Microsoft Office Outlook (Outlook Client)</p>
<p>Once you go ahead and download the file the setup would prompt you to restart outlook.</p>
<p>Run the &lsquo;Configuration Wizard&rsquo; you see in your Program Files (Another method to run the configuration wizard would be to open your outlook as well)</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4035.5.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4035.5.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4035.5.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4035.5.png" alt="" border="0" /></a></p>
<p><em>Fig: 5 - Opening the Configuration Wizard from the Start Menu</em></p>
<p>The configuration wizard would pull up the wizard below.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4863.6.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4863.6.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4863.6.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4863.6.png" alt="" border="0" /></a></p>
<p><em>Fig: 6 - Wizard</em></p>
<p>Change the &lsquo;Server URL&rsquo; to CRM online</p>
<p>Authenticate as a user who is a CRM Administrator</p>
<p>Go ahead and &lsquo;Test Connection&rsquo;</p>
<p>Once the connection has been tested, it would pull out all the organizations that is part of the O365 account.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8311.7.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8311.7.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8311.7.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8311.7.png" alt="" border="0" /></a></p>
<p><em>Fig: 7&nbsp;- Configuring an organization for your Outlook Client</em></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7206.8.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7206.8.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7206.8.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7206.8.png" alt="" border="0" /></a></p>
<p><em>Fig: 8 - Once the credentials are given, the organization would be synchronized with Outlook</em></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2311.9.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2311.9.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2311.9.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2311.9.png" alt="" border="0" /></a></p>
<p><em>Fig: 9 - Confirmation window</em></p>
<p>Now if you go ahead and restart your outlook, you will find a new tab to synchronize your CRM organization.</p>
<p>Once that is done, you will find &lsquo;Contoso&rsquo; CRM organization as part of your Outlook.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/0726.10.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/0726.10.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/0726.10.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/0726.10.png" alt="" border="0" /></a></p>
<p><em>Fig: 10 - CRM tab within your Outlook</em></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3632.11.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3632.11.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3632.11.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3632.11.png" alt="" border="0" /></a></p>
<p><em>Fig: 11 - On the left both emails as well as your CRM organization can be viewed</em></p>
<p>Post which you can</p>
<ol>
<li>
<div>Track emails received by CRM contacts</div>
</li>
<li>
<div>Set emails regarding a contact/account/lead in CRM</div>
</li>
<li>
<div>Convert emails into leads</div>
</li>
</ol>
<p>You can even use the Outlook Client started in the background and sending mails from the CRM Web-Client</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2251.12.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2251.12.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2251.12.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2251.12.png" alt="" border="0" /></a></p>
<p><em>Fig: 12- On the top right of the above snapshot, you can go ahead and &lsquo;track&rsquo; or &lsquo;set regarding&rsquo;</em></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2185.13.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2185.13.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2185.13.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2185.13.png" alt="" border="0" /></a></p>
<p><em>Fig: 13 - The snapshot above shows an example where an email has been tracked to an associated contact.</em></p>
<p>I hope this helps. Please keep watching for the second part of this article which would be on configuring Email Router for Exchange.</p>
<p>&nbsp;</p>
