---
layout: post
title: Mailing Systems in CRM 2011 Demystified - Part 3
date: 2013-05-30 14:43
author: sivakumar v
comments: true
categories: [Aishwarya C Ramachandran, Articles, CRM 2011, CRM for Outlook, CRM Online, Email Router, Exchange Server, Forward Mailbox, Office 365, Outlook, Outlook Client, Uncategorized]
---
<p style="text-align: left;"><a title="Aishwarya C Ramachandran - Click for blog homepage"><img src="https://microsofttpd.github.io/assets/3225.aishram.jpg" original-url="https://microsofttpd.github.io/assets/3225.aishram.jpg" alt="Aishwarya C Ramachandran - Click for blog homepage" width="80" height="95" align="right" border="0" hspace="10" /></a><a title="http://blogs.technet.com/258186/ProfileUrlRedirect.ashx" href="http://blogs.technet.com/258186/ProfileUrlRedirect.ashxAishwarya Ramachandran" target="_blank">Aishwarya Ramachandran</a> continues her series of articles on Mailing Systems in CRM 2011 Demystified with the third and last article in the series now.</p>
<p>The earlier parts can be accessed from the links below.</p>
<ul>
<li><a title="https://microsofttpd.github.io/archive/2013/05/22/mailing-systems-in-crm-2011-demystified-part-1.aspx" href="https://microsofttpd.github.io/archive/2013/05/22/mailing-systems-in-crm-2011-demystified-part-1.aspxMailing Systems in CRM 2011 Demystified - Part 1" target="_blank">Mailing Systems in CRM 2011 Demystified - Part 1</a></li>
<li><a title="Mailing Systems in CRM 2011 Demystified - Part 2" href="https://microsofttpd.github.io/archive/2013/05/29/mailing-systems-in-crm-2011-demystified-part-2.aspx" target="_blank">Mailing Systems in CRM 2011 Demystified - Part 2</a></li>
</ul>
<p>The third part of this series covers configuring the E-mail Router to use a forward mailbox .<em><strong>This allows one central mailbox to monitor, instead of monitoring the mailbox of each user who needs Microsoft Dynamics CRM e-mail capabilities.</strong></em></p>
<p>For large organizations configuration of 2 profiles for each user would prove to be a tremendous load on the server with the email router.</p>
<p>When you use forward mailbox monitoring, incoming messages are processed by Microsoft Exchange Server or the POP3 server and the E-mail Router in the following sequence:</p>
<ol>
<li>A message is received by a Microsoft Dynamics CRM user or queue mailbox, on either the Exchange Server or the POP3 server.</li>
<li>A rule in the user's mailbox sends a copy of the message to the Microsoft Dynamics CRM forward mailbox.</li>
<li>The E-mail Router retrieves the message from the Microsoft Dynamics CRM forward mailbox and sends it to the computer that is running Microsoft Dynamics CRM Server 2011.</li>
</ol>
<p>You can find information on the forward mailbox in this document:-</p>
<ul>
<li><a title="Microsoft Dynamics CRM 2011 for E-mail Router Installing Guide for use with Microsoft Dynamics CRM Online" href="http://www.microsoft.com/en-us/download/details.aspx?id=18991" target="_blank">Microsoft Dynamics CRM 2011 for E-mail Router Installing Guide for use with Microsoft Dynamics CRM Online</a></li>
</ul>
<p><strong>How can we set up a forward mailbox from O365?</strong></p>
<p><strong>Step 1:</strong></p>
<p>Create a forward mailbox as a user in your O365</p>
<p>1.&nbsp;Create a user in O365 by first navigating to &ldquo;Users and Groups&rdquo; in the O365 portal</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4186.1.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4186.1.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4186.1.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4186.1.png" alt="" border="0" /></a></p>
<p><em>Fig:&nbsp; 1 &ndash; Navigating to &ldquo;Users and Groups&rdquo; in the O365 Portal</em></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/5165.2.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/5165.2.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/5165.2.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/5165.2.png" alt="" border="0" /></a></p>
<p><em>Fig:&nbsp; 2 &ndash; Creating a user by clicking on the &ldquo;+&rdquo; sign</em></p>
<p>2.&nbsp;You can go ahead and create a new user by clicking on the &ldquo;+&rdquo; sign above all the users of O365</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7024.3.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7024.3.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7024.3.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7024.3.png" alt="" border="0" /></a>&nbsp;<br /><em>Fig:&nbsp; 3 &ndash; Filling out the details of the user with the forward mailbox ID</em></p>
<p>3.&nbsp;Ensure that when you go ahead and fill out the details of the new user specify the email address of the forward mailbox that you wish to create.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7142.4.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7142.4.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7142.4.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7142.4.png" alt="" border="0" /></a>&nbsp;<br /><em>Fig:&nbsp; 4 &ndash; Filling out the details of the user with the forward mailbox ID</em></p>
<p>4.&nbsp;The next window would prompt you to fill out the role and the location of the user in O365.</p>
<p><em><strong>PS:</strong> It is not mandatory that this user needs a role in your CRM organization.</em></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8407.5.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8407.5.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8407.5.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8407.5.png" alt="" border="0" /></a><br /><em>Fig:&nbsp; 5 &ndash; Getting a license for your user</em></p>
<p>5.&nbsp;This window would get a license for your user with the forward mailbox.</p>
<p><em><strong>PS:</strong> It is not mandatory that this user must have a license in CRM online</em></p>
<p><em><strong>Post this you would receive the password of this user in your admin account.</strong></em></p>
<p><strong>Step 2:</strong>&nbsp;&nbsp;</p>
<p>Ensure that the user is configured to utilize &lsquo;E-mail Router&rsquo;</p>
<p>To configure you should navigate to:-</p>
<p><em>Settings &gt;&gt; Administration &gt;&gt; Users &gt;&gt; *Open the user&rsquo;s record&rsquo; &gt;&gt; Scroll to the middle and look for &ldquo;Email access type &ndash; Incoming&rdquo;</em></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3364.6.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3364.6.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3364.6.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3364.6.png" alt="" border="0" /></a></p>
<p><em>Fig: 6 - A section of a user record in CRM online</em></p>
<p>The email address given in the user record must be approved by the CRM Administrator.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/6082.7.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/6082.7.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/6082.7.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/6082.7.png" alt="" border="0" /></a>&nbsp;</p>
<p><em>Fig: 7 - Approving a user&rsquo;s email ID from within the users record</em></p>
<p><strong>Step 3:</strong>&nbsp;</p>
<p>Once you have created a forward mailbox and configured your user to utilize the forward mailbox, the next step would be to create a forwarding Rule in your User inbox</p>
<p>1.&nbsp;Login to the users O365 portal and click on &ldquo;Outlook&rdquo; tab present on the top middle.</p>
<p>2.&nbsp;Once you see the OWA go ahead and click on the users options beside the settings icon on the top right as seen in the snapshot below</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8015.8.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8015.8.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8015.8.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8015.8.png" alt="" border="0" /></a></p>
<p><em>Fig: 8-Click on &ldquo;Options&rdquo; when you log on to the users OWA</em></p>
<p>3.&nbsp;Click on &ldquo;Organize Email&rdquo; that can be found on the sidebar</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2744.9.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2744.9.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2744.9.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2744.9.png" alt="" border="0" /></a></p>
<p><em>Fig: 9-Click on &ldquo;Organize Email&rdquo; when you log on to the users OWA</em></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2110.10.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2110.10.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2110.10.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2110.10.png" alt="" border="0" /></a></p>
<p><em>Fig: 10-Click on &ldquo;Organize Email&rdquo; when you log on to the users OWA</em></p>
<p>4.&nbsp;Create a rule for &ldquo;Create a new rule for arriving messages&rdquo; as shown in the snapshot above.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4745.11.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4745.11.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4745.11.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4745.11.png" alt="" border="0" /></a></p>
<p><em>Fig: 11-The window above would be seen once you go ahead and create a new rule</em></p>
<p>5.&nbsp;The above window would ask which messages this rule must be applied to. Click on &ldquo;More Options&rdquo; you see at the bottom of the window.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/6052.12.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/6052.12.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/6052.12.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/6052.12.png" alt="" border="0" /></a></p>
<p><em>Fig: 12-The above options would appear once you click on &ldquo;More options&rdquo; as suggested in the previous point</em></p>
<p>6.&nbsp;Select on &ldquo;Forward the message as an attachment&rdquo;</p>
<p>7.&nbsp;The next window would prompt you to select a mailbox to which you would like to forward all the users emails to.&nbsp;</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7103.13.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7103.13.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7103.13.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7103.13.png" alt="" border="0" /></a></p>
<p><em>Fig: 13-Selecting the user with the forward mailbox</em></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/6708.14.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/6708.14.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/6708.14.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/6708.14.png" alt="" border="0" /></a></p>
<p><em>Fig: 14-A rule is created in the users inbox</em></p>
<p>8.&nbsp;The above snapshot shows the rule created where the user&rsquo;s emails would be forwarded to the forward mailbox.</p>
<p><strong>Step 4:</strong>&nbsp;</p>
<p><strong>Create an incoming and outgoing profile exclusively for the forward mailbox</strong></p>
<p>1.&nbsp;Create an incoming profile for the Forward mailbox as shown.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4135.15.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4135.15.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4135.15.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4135.15.png" alt="" border="0" /></a></p>
<p><em>Fig: 15-Creating an incoming profile for the forward mailbox</em></p>
<p>2.&nbsp;Create an outgoing profile for the forward mailbox.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/0333.16.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/0333.16.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/0333.16.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/0333.16.png" alt="" border="0" /></a></p>
<p><em>Fig: 16-Creating an incoming profile for the forward mailbox</em></p>
<p>3.&nbsp;Creating a new deployment for in the email router.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7558.17.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7558.17.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/7558.17.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/7558.17.png" alt="" border="0" /></a></p>
<p><em>Fig: 17-Deployment in the email router</em></p>
<p>4.&nbsp;Once you go ahead and load the data you would get all the users that use the email router as the outgoing or the incoming profile.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/0363.18.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/0363.18.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/0363.18.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/0363.18.png" alt="" border="0" /></a></p>
<p><em>Fig: 18-All the users that would be pulled up when data is loaded</em></p>
<p>5.&nbsp;If I open up the user record we can see that the incoming would be greyed out (as in the CRM system I had chosen the email router)</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2275.19.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2275.19.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2275.19.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2275.19.png" alt="" border="0" /></a><br /><em>Fig: 19-The window I would see if I double click the &ldquo;CRM System&rdquo; user</em></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4478.20.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4478.20.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4478.20.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4478.20.png" alt="" border="0" /></a></p>
<p><em>Fig: 20-Go ahead and click on the tab &ldquo;Forward Mailbox&rdquo;</em></p>
<p>6.&nbsp;Beside the &ldquo;Users and Queues&rdquo; tab you would see another tab called the &ldquo;Forward Mailbox&rdquo;</p>
<p>7.&nbsp;Go ahead and click on &ldquo;New&rdquo; under the &ldquo;Forward Mailbox&rdquo; Tab.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4214.21.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4214.21.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4214.21.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4214.21.png" alt="" border="0" /></a></p>
<p><em>Fig: 21-Create a new profile for the new forward mailbox</em></p>
<p>8.&nbsp;Once a new profile is created you would see this profile under the &ldquo;Forward Mailbox&rdquo; Tab</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2781.22.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2781.22.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2781.22.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2781.22.png" alt="" border="0" /></a></p>
<p><em>Fig: 22-The new forward mailbox created</em></p>
<p>9.&nbsp;Once this is done go ahead and test access and the forward mailbox would be configured.&nbsp;</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3582.23.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3582.23.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3582.23.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3582.23.png" alt="" border="0" /></a></p>
<p><em>Fig: 23-Test access succeeded for the forward mailbox</em>&nbsp;</p>
<p><strong>Tips:</strong></p>
<ul>
<li>
<div>When an email is sent to this user a copy of the email would remain in the forward mailbox; Provided that the &ldquo;Delete messages in forward mailbox after processing&rdquo; is not checked(Fig 19)</div>
</li>
<li>
<div>Sometimes a setting would have to be done in order to view all these emails in your CRM system.</div>
</li>
<ul>
<li>
<div>Go to your users CRM system and click on &ldquo;Options&rdquo; on the top left</div>
</li>
</ul>
</ul>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/5241.24.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/5241.24.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/5241.24.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/5241.24.png" alt="" border="0" /></a></p>
<p><em>Fig: 24-Click on &ldquo;Options&rdquo; found at the top left</em></p>
<ul>
<ul>
<li>
<div>Ensure that the &ldquo;Track&rdquo; setting is set to &ldquo;All e-mail messages&rdquo;</div>
</li>
</ul>
</ul>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4201.25.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4201.25.png"><img src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/4201.25.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/4201.25.png" alt="" border="0" /></a></p>
<p><em>Fig: 23-Ensure that all the emails messages are tracked</em></p>
<p>Now your forward mailbox has been set and all the emails should get tracked and received in the user&rsquo;s mailbox. The huge advantage is that there is now only 1 mailbox to monitor!</p>
