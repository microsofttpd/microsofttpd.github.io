---
layout: post
title: Microsoft Dynamics CRM Connector for NAV- Step by Step Guide to Installation & Configuration
date: 2013-10-22 10:34
author: trapti nagar
comments: true
categories: [Articles, Connector, CRM 2011, CRM Connector, CRM Integration, CRM Online, NAV 2013, Trapti Nagar, Uncategorized]
---
<p style="text-align: left;"><a title="Trapti Nagar - Click for blog homepage" href="https://microsofttpd.github.io/"><img src="https://microsofttpd.github.io/assets/0601.traptin.png" original-url="http://blogs.technet.com/cfs-filesystemfile.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09-images/0601.traptin.png" alt="Trapti Nagar - Click for blog homepage" width="80" height="110" align="right" border="0" hspace="10" /></a>This blog post gives step by step procedures to integrate Dynamics CRM 2011/CRM online with NAV 2013.</p>
<p><strong>Note:</strong> Download the connector setup and installation guide from links mentioned in the last section.</p>
<p><strong>Prerequisites<br /></strong><strong></strong></p>
<p><strong>Microsoft Dynamics CRM</strong></p>
<p>Create two Windows Live ID accounts for CRM online or two user accounts for Dynamics CRM on premise for following types of users:</p>
<ul>
<li>Admin User</li>
<li>Integration User (assign <strong>System Customizer </strong>role after creating a user in short)</li>
</ul>
<p><strong>Setup Dynamics NAV to <a href="http://blogs.technet.com/controlpanel/blogs/posteditor.aspx/">enable Data Synchronization</a></strong></p>
<ul>
<li>To turn on integration and enable synchronization, run through following steps:</li>
<li>Start Microsoft Dynamics NAV and in the search box, enter <strong>Marketing Setup</strong>.</li>
<li>Open the <strong>Marketing Setup</strong> window.</li>
<li>On the <strong>Synchronization</strong> FastTab, select the <strong>Enable Connector</strong> check box. Click <strong>Yes</strong> to confirm.</li>
<li>Exit and start Microsoft Dynamics NAV again before you configure Connector for Microsoft Dynamics.</li>
<li>After you enable Connector for Microsoft Dynamics, verify that the following services are started:</li>
<ul>
<li>Microsoft Dynamics NAV Business Web Services</li>
<li>Microsoft Dynamics NAV Server</li>
</ul>
</ul>
<p><strong>Installation and configuration</strong></p>
<p>Run the setup, click next.</p>
<p><a href="https://microsofttpd.github.io/assets/5282.image_40B4708C.png" original-url="https://microsofttpd.github.io/assets/5282.image_5F00_40B4708C.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/8358.image_thumb_7B2F7060.png" original-url="https://microsofttpd.github.io/assets/8358.image_5F00_thumb_5F00_7B2F7060.png" alt="image" width="500" height="386" border="0" /></a></p>
<p>Give the name of your Dynamics NAV SQL server</p>
<p><a href="https://microsofttpd.github.io/assets/3000.image_66ACB193.png" original-url="https://microsofttpd.github.io/assets/3000.image_5F00_66ACB193.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/2477.image_thumb_6810D465.png" original-url="https://microsofttpd.github.io/assets/2477.image_5F00_thumb_5F00_6810D465.png" alt="image" width="500" height="298" border="0" /></a></p>
<p>Provide administrator account credentials for NAV/System</p>
<p><a href="https://microsofttpd.github.io/assets/7612.image_733CEF60.png" original-url="https://microsofttpd.github.io/assets/7612.image_5F00_733CEF60.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/2352.image_thumb_49C8AE20.png" original-url="https://microsofttpd.github.io/assets/2352.image_5F00_thumb_5F00_49C8AE20.png" alt="image" width="503" height="299" border="0" /></a></p>
<p>Click to install.</p>
<p><a href="https://microsofttpd.github.io/assets/1731.image_791A23AA.png" original-url="https://microsofttpd.github.io/assets/1731.image_5F00_791A23AA.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/2766.image_thumb_3D5D1BA8.png" original-url="https://microsofttpd.github.io/assets/2766.image_5F00_thumb_5F00_3D5D1BA8.png" alt="image" width="503" height="390" border="0" /></a></p>
<p>It will start to install dynamics connector.</p>
<p><a href="https://microsofttpd.github.io/assets/0131.image_6CAE9132.png" original-url="https://microsofttpd.github.io/assets/0131.image_5F00_6CAE9132.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/8510.image_thumb_5EDEDBE8.png" original-url="https://microsofttpd.github.io/assets/8510.image_5F00_thumb_5F00_5EDEDBE8.png" alt="image" width="500" height="384" border="0" /></a></p>
<p><a href="https://microsofttpd.github.io/assets/4336.image_0E305173.png" original-url="https://microsofttpd.github.io/assets/4336.image_5F00_0E305173.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/3034.image_thumb_046AE9FB.png" original-url="https://microsofttpd.github.io/assets/3034.image_5F00_thumb_5F00_046AE9FB.png" alt="image" width="499" height="386" border="0" /></a></p>
<p>You will reach finish screen, if everything goes fine.</p>
<p><a href="https://microsofttpd.github.io/assets/0334.image_769B34B0.png" original-url="https://microsofttpd.github.io/assets/0334.image_5F00_769B34B0.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/1362.image_thumb_087A592F.png" original-url="https://microsofttpd.github.io/assets/1362.image_5F00_thumb_5F00_087A592F.png" alt="image" width="491" height="378" border="0" /></a></p>
<p>You need to install the <strong>ConnectorForMicrosoftDynamicsNav </strong>solution in your CRM organization to enable CRM instance to support NAV data integration. Follow the steps mentioned below:</p>
<p>1. Log on to an organization in Microsoft Dynamics CRM as an administrator.</p>
<p>2. In the navigation pane, go to <strong>Settings </strong>&gt; <strong>Customization </strong>&gt; <strong>Solutions</strong>. Click <strong>Import</strong>.</p>
<p>3. Browse to the Connector installation directory (\Program Files\Microsoft Dynamics\Microsoft Dynamics Adapter).</p>
<p>4. Select the <strong>ConnectorForMicrosoftDynamicsNav.zip </strong>solution file. Click <strong>Open. </strong></p>
<p>5. Click <strong>Next</strong>. When the <strong>Solution Information </strong>is displayed, a message might be displayed that warns of a version mismatch. Click <strong>Next</strong>.</p>
<p>6. Select <strong>Activate any processes and enable any SDK message processing steps included in the solution</strong>.</p>
<p><strong>Note: </strong>If you do not select this check box, the steps to install the plug-in will not be activated and the process cannot be completed.</p>
<p>7. Click <strong>Next</strong>.</p>
<p>8. When the solution customizations have been successfully imported, click <strong>Close </strong>to exit.</p>
<p><a href="https://microsofttpd.github.io/assets/0247.image_577AA881.png" original-url="https://microsofttpd.github.io/assets/0247.image_5F00_577AA881.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/7140.image_thumb_04FE58F6.png" original-url="https://microsofttpd.github.io/assets/7140.image_5F00_thumb_5F00_04FE58F6.png" alt="image" width="496" height="358" border="0" /></a></p>
<p><a href="https://microsofttpd.github.io/assets/4774.image_5AB1B1CB.png" original-url="https://microsofttpd.github.io/assets/4774.image_5F00_5AB1B1CB.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/4721.image_thumb_018258BD.png" original-url="https://microsofttpd.github.io/assets/4721.image_5F00_thumb_5F00_018258BD.png" alt="image" width="496" height="381" border="0" /></a></p>
<p>After importing the solution, follow the steps below to give adapter settings:</p>
<p>1. Start-&gt; connector for Microsoft dynamics</p>
<p>2. Run the connector</p>
<p>3. Click on adapter settings on top menu</p>
<p><strong>4. </strong>Give the following information in <strong>Dynamics CRM 2011</strong> for online, else give the setting in <strong>Dynamics CRM</strong></p>
<p>Note that the user given here integration user we have already created.</p>
<p><a href="https://microsofttpd.github.io/assets/5756.image_0C4240C3.png" original-url="https://microsofttpd.github.io/assets/5756.image_5F00_0C4240C3.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/7840.image_thumb_3B93B64D.png" original-url="https://microsofttpd.github.io/assets/7840.image_5F00_thumb_5F00_3B93B64D.png" alt="image" width="498" height="332" border="0" /></a></p>
<p>Click on test settings, after you see a success message click on link to configuration utility.</p>
<p>You will see a screen like this.</p>
<p><a href="https://microsofttpd.github.io/assets/6131.image_18D27E90.png" original-url="https://microsofttpd.github.io/assets/6131.image_5F00_18D27E90.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/6012.image_thumb_11B5D2C9.png" original-url="https://microsofttpd.github.io/assets/6012.image_5F00_thumb_5F00_11B5D2C9.png" alt="image" width="498" height="266" border="0" /></a></p>
<p>The configuration settings will take the URL automatically, just give username (here use administrator credentials) and password and click on <strong>Get organizations. </strong>You should be able to get the organization name in the highlighted area in which you want to implement the integration as shown in the screenshot.</p>
<p><a href="https://microsofttpd.github.io/assets/0753.image_47BA51D6.png" original-url="https://microsofttpd.github.io/assets/0753.image_5F00_47BA51D6.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/0131.image_thumb_770BC760.png" original-url="https://microsofttpd.github.io/assets/0131.image_5F00_thumb_5F00_770BC760.png" alt="image" width="470" height="278" border="0" /></a></p>
<p>Finish the CRM configuration utility wizard and click on <strong>Microsoft Dynamics NAV </strong>in the adapter settings as shown below.</p>
<p>Credentials to be used are mentioned here:</p>
<p><strong>Domain</strong>: Enter your Windows domain.</p>
<p><strong>User Name</strong>: Enter your Windows user name or alias.</p>
<p><strong>Password</strong>: Enter your domain password.</p>
<p><strong>URL</strong>: <a href="http://localhost:7047/DynamicsNAV/WS/">http://localhost:7047/DynamicsNAV/WS/</a></p>
<p><strong>(Note: In some cases we might face errors in connecting the NAV and it fails, try giving server IP address in place of localhost in the URL as shown in screenshot below)</strong></p>
<p><a href="https://microsofttpd.github.io/assets/0564.image_544A8FA3.png" original-url="https://microsofttpd.github.io/assets/0564.image_5F00_544A8FA3.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/0842.image_thumb_25F39AA7.png" original-url="https://microsofttpd.github.io/assets/0842.image_5F00_thumb_5F00_25F39AA7.png" alt="image" width="466" height="304" border="0" /></a></p>
<p>This is the success message screen</p>
<p><a href="https://microsofttpd.github.io/assets/4604.image_1823E55D.png" original-url="https://microsofttpd.github.io/assets/4604.image_5F00_1823E55D.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/2577.image_thumb_15118768.png" original-url="https://microsofttpd.github.io/assets/2577.image_5F00_thumb_5F00_15118768.png" alt="image" width="462" height="293" border="0" /></a></p>
<p>Click on test settings, after you see a success message click on link to configuration utility.</p>
<p>Give the credentials and select the Dynamics NAV Organization.</p>
<p>Select the entities you want to enable for integration.</p>
<p><a href="https://microsofttpd.github.io/assets/8206.image_393972A8.png" original-url="https://microsofttpd.github.io/assets/8206.image_5F00_393972A8.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/3858.image_thumb_362714B3.png" original-url="https://microsofttpd.github.io/assets/3858.image_5F00_thumb_5F00_362714B3.png" alt="image" width="457" height="293" border="0" /></a></p>
<p><a href="https://microsofttpd.github.io/assets/8611.image_61020976.png" original-url="https://microsofttpd.github.io/assets/8611.image_5F00_61020976.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/3362.image_thumb_72E12DF4.png" original-url="https://microsofttpd.github.io/assets/3362.image_5F00_thumb_5F00_72E12DF4.png" alt="image" width="481" height="286" border="0" /></a></p>
<p>After the process is finished click in create new integration. Give the details as given in the below screenshot.</p>
<p><a href="https://microsofttpd.github.io/assets/2543.image_372425F2.png" original-url="https://microsofttpd.github.io/assets/2543.image_5F00_372425F2.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/5238.image_thumb_1B15F7B8.png" original-url="https://microsofttpd.github.io/assets/5238.image_5F00_thumb_5F00_1B15F7B8.png" alt="image" width="481" height="342" border="0" /></a></p>
<p>Now you can start creating new maps.</p>
<p><a href="https://microsofttpd.github.io/assets/5773.image_2CF51C36.png" original-url="https://microsofttpd.github.io/assets/5773.image_5F00_2CF51C36.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/3157.image_thumb_0A33E479.png" original-url="https://microsofttpd.github.io/assets/3157.image_5F00_thumb_5F00_0A33E479.png" alt="image" width="487" height="348" border="0" /></a></p>
<p><a href="https://microsofttpd.github.io/assets/0207.image_006E7D01.png" original-url="https://microsofttpd.github.io/assets/0207.image_5F00_006E7D01.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/3225.image_thumb_44B174FE.png" original-url="https://microsofttpd.github.io/assets/3225.image_5F00_thumb_5F00_44B174FE.png" alt="image" width="487" height="299" border="0" /></a></p>
<p>Make sure that you create necessary maps first. Have a look at the installation guide for more information.</p>
<p><a href="https://microsofttpd.github.io/assets/6866.image_189708BE.png" original-url="https://microsofttpd.github.io/assets/6866.image_5F00_189708BE.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/0552.image_thumb_47E87E48.png" original-url="https://microsofttpd.github.io/assets/0552.image_5F00_thumb_5F00_47E87E48.png" alt="image" width="503" height="274" border="0" /></a></p>
<p>After the Connector for Microsoft Dynamics is installed and the adapters are configured, data needs to be synchronized between Microsoft Dynamics CRM and Microsoft Dynamics NAV before you can run integrations on a regular schedule.</p>
<p>Verify that the customizations have been deployed as outlined in the Basic installation section, to check this create one entity record and see if you are able to see the submit button on the ribbon as highlighted in the screenshot below.</p>
<p><a href="https://microsofttpd.github.io/assets/2654.image_59C7A2C6.png" original-url="https://microsofttpd.github.io/assets/2654.image_5F00_59C7A2C6.png"><img style="display: inline; border-width: 0px;" title="image" src="https://microsofttpd.github.io/assets/2133.image_thumb_09191851.png" original-url="https://microsofttpd.github.io/assets/2133.image_5F00_thumb_5F00_09191851.png" alt="image" width="444" height="352" border="0" /></a></p>
<p>The Connector for Microsoft Dynamics is designed to integrate data between Microsoft Dynamics NAV and Microsoft Dynamics CRM in the following scenarios:</p>
<ul>
<li>New Microsoft Dynamics NAV and Microsoft Dynamics CRM application installations</li>
<li>Existing Microsoft Dynamics NAV installation and new Microsoft Dynamics CRM installation or Existing Microsoft Dynamics CRM installation and new Microsoft Dynamics NAV installation</li>
<li>Both Microsoft Dynamics NAV and Microsoft Dynamics CRM existing installations</li>
</ul>
<p>Data could exist in one or both applications. You must synchronize this data prior to running the integration on a regular schedule.</p>
<p>Now you are done with the integration, schedule the Data synchronization process and validate the data.</p>
<p><strong>Quick Links</strong></p>
<p>Here are some useful links to quickly access resources:</p>
<p><a href="http://msdn.microsoft.com/en-us/library/gg502460.aspx" target="_blank">http://msdn.microsoft.com/en-us/library/gg502460.aspx</a></p>
<p><a href="http://msdn.microsoft.com/en-us/library/gg481835.aspx" target="_blank">http://msdn.microsoft.com/en-us/library/gg481835.aspx</a></p>
<p><a href="http://blogs.msdn.com/b/dynamicsconnector/" target="_blank">http://blogs.msdn.com/b/dynamicsconnector/</a></p>
<p><a href="http://www.microsoft.com/en-in/download/details.aspx?id=10381" target="_blank">http://www.microsoft.com/en-in/download/details.aspx?id=10381</a></p>
<p><a title="https://mbs.microsoft.com/partnersource/deployment/resources/productreleases/MDNAV2009R2_CRMConnector.htm" href="https://mbs.microsoft.com/partnersource/deployment/resources/productreleases/MDNAV2009R2_CRMConnector.htm" target="_blank">https://mbs.microsoft.com/partnersource/deployment/resources/productreleases/MDNAV2009R2_CRMConnector.htm</a></p>
