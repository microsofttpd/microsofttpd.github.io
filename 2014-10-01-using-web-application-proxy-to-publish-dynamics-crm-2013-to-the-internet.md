---
layout: post
title: Using Web Application Proxy to Publish Dynamics CRM 2013 to the internet
date: 2014-10-01 08:37
author: corey hanson
comments: true
categories: [ADFS, Articles, Corey Hanson, Dynamics CRM 2013, Uncategorized, WAP, Windows Server 2012 R2]
---
<p style="text-align: left"><a title="Sivakumar Venkataraman - Click for blog homepage"><img src="https://microsofttpd.github.io/assets/8203.chanson.jpg" alt="Sivakumar Venkataraman - Click for blog homepage" width="80" height="95" align="right" border="0" hspace="10" /></a>With the release of Windows Server 2012 R2 there is a new server role called <a href="http://technet.microsoft.com/en-us/library/dn584107.aspx" target="_blank">Web Application Proxy</a> (WAP).  The WAP server role functions as the ADFS Proxy as well.  In customer scenarios where a DMZ/perimeter network is used the common issue is how to get Dynamics CRM published to the internet.</p>
One option you have is to put the CRM Front End server in the DMZ, but the main problem with this is the CRM server is required to be domain joined, which is usually a no-no for a DMZ.  So in the past some options included ISA or UAG but those products are being phased out.  So now we have the WAP server role.  This can be used to publish the CRM URLs needed for internet facing access.

The rest of this post will walk through the WAP configuration and publishing the CRM URLs. This post assumes you have already setup ADFS internally and you already have Dynamics CRM installed and configured for IFD and now you just need to publish your CRM URLs to the internet.

<strong>Import ADFS Certificate</strong>

On the WAP server we need to import the certificate you are using on the ADFS server into the Personal Certificate store of the WAP server.  We will need this certificate later during the configuration and publishing the CRM URLs. Export the certificate from the ADFS server and import it into the WAP server.  Your certificate should be listed in the Personal store.

<a href="https://microsofttpd.github.io/assets/image_1A173F01.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_2306D140.png" alt="image" width="244" height="113" border="0" /></a>

<strong>Add the WAP role to the non domain joined server in the DMZ/perimeter network</strong>

In Server Manager - Click Manage and Choose Add Roles and Features.

<a href="https://microsofttpd.github.io/assets/image_6983C148.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_44F233C4.png" alt="image" width="244" height="75" border="0" /></a>

Except the defaults and when you get to the Server Roles section select Remote Access.

<a href="https://microsofttpd.github.io/assets/image_59778342.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_7FD9668D.png" alt="image" width="244" height="153" border="0" /></a>

Then select Web Application Proxy and finish the wizard.

<a href="https://microsofttpd.github.io/assets/image_5B47D909.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_7D9F6E82.png" alt="image" width="244" height="125" border="0" /></a>

<strong>Configure WAP role</strong>

Once the WAP role is installed you will have a Remote Access Management program on your start screen.  Launch it to start the configuration.

<a href="https://microsofttpd.github.io/assets/image_7D333B8D.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_51827191.png" alt="image" width="244" height="111" border="0" /></a>

For the Federation service name enter in the URL you setup when configuring your ADFS server. (For example sts.domain.com or adfs.domain.com).  Then enter in a local admin account that you have on the ADFS server.

<a href="https://microsofttpd.github.io/assets/image_7F039154.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_4F487986.png" alt="image" width="244" height="114" border="0" /></a>

Select the certificate that you installed on the WAP server.  This will be the certificate you used on the ADFS server as well.  Then finish the wizard to complete the configuration.

<a href="https://microsofttpd.github.io/assets/image_67D816D6.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_232B7C95.png" alt="image" width="244" height="53" border="0" /></a>

<strong>Errors</strong>

If you have issues with the WAP configuration not connecting or finding the ADFS server.  Make sure your hosts file on the WAP server is updated to include the IP address of the ADFS server to resolve the ADFS URL.  Also verify you are using the correct ADFS URL that you created during the ADFS configuration.

<a href="https://microsofttpd.github.io/assets/image_09C3795B.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_4C361B91.png" alt="image" width="244" height="60" border="0" /></a>

<strong>Publish CRM URLs</strong>

Now we will publish the CRM URLs in the Remote Access Management Console.  Select the Web Application Proxy under configuration and then click Publish.

<a href="https://microsofttpd.github.io/assets/image_47BF9ACA.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_40342B5D.png" alt="image" width="244" height="50" border="0" /></a>

Select Pass-through.  We do not want the WAP to do any pre-authentication.  We just need the URL to pass through to CRM and then CRM will redirect to ADFS to get the claims needed to successfully login.

<a href="https://microsofttpd.github.io/assets/image_3BBDAA96.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_24FE630D.png" alt="image" width="244" height="85" border="0" /></a>

Enter in a friendly name for the URL.  Then Enter in the external org URL.  Select the certificate which will be the same certificate you uploaded earlier.  Enter in the same org  URL for the Backend server URL.  Then confirm the settings and click Publish.

<a href="https://microsofttpd.github.io/assets/image_4B604658.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_34A0FECF.png" alt="image" width="244" height="121" border="0" /></a>

Do the same for the Auth URL.

<a href="https://microsofttpd.github.io/assets/image_3434CBDA.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_088401DE.png" alt="image" width="244" height="124" border="0" /></a>

Do the same for the DEV/Discovery URL.

<a href="https://microsofttpd.github.io/assets/image_360521A1.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_0A5457A5.png" alt="image" width="244" height="116" border="0" /></a>

Once the three CRM URLs are published you should have 3 Published Web Applications.

<strong>Disable URL Translation</strong>

Now there is one additional step we need to do to make this work.  We need to Disable URL translation.  The reason we have to do this is the WAP will re-scope the cookies as part of the URL translation and CRM leverages a domain cookie that can be shared across sub-domains.  If URL translation is not disabled access to CRM will be prevented.  Disabling URL translation will allow the WAP role to pass the cookie along that CRM is expecting.

The first thing we need to do is get the ID of each of the CRM published URLs we added above.  We do not need to disable URL translation on the adfs url.

To do this launch PowerShell in Administrator mode and run

Get-WebApplicationProxyApplication Name* | Format-List

Replace Name* with the name or part of the name of one of your URL’s.  Like Dynamics* would find all URL’s that have Dynamics at the beginning.  Using Format-List will list out the results much nicer and make it easier to copy the ID out.

<a href="https://microsofttpd.github.io/assets/image_5EA61E59.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_1E03D1EA.png" alt="image" width="244" height="101" border="0" /></a>

Command to Disable URL Translation

Once you have the ID for each of the URLs run this command replacing GUID with the ID you copied from above.

Set-WebApplicationProxyApplication –ID GUID –DisableTranslateUrlInResponseHeaders

<a href="https://microsofttpd.github.io/assets/image_275F971E.png"><img style="padding-top: 0px;padding-left: 0px;margin: 0px;padding-right: 0px;border-width: 0px" title="image" src="https://microsofttpd.github.io/assets/image_thumb_26F36429.png" alt="image" width="244" height="26" border="0" /></a>

<strong>External DNS</strong>

Final step is to make sure your external DNS records for each of these URLs points to the WAP server now.
<ul>
	<li>External Org URL</li>
	<li>Auth URL</li>
	<li>Dev URL</li>
	<li>ADFS URL</li>
</ul>
<strong>THANKS:  </strong>I also want to give credit to Jason on his post here that initially help me out:

<a href="http://blogs.msdn.com/b/javaller/archive/2014/01/13/publishing-crm-internet-facing-deployment-using-web-application-proxy-and.aspx" target="_blank">http://blogs.msdn.com/b/javaller/archive/2014/01/13/publishing-crm-internet-facing-deployment-using-web-application-proxy-and.aspx</a>

4/1/16 Update: Removed the steps to publish the AFDS URL as that is already established with WAP and ADFS.  Thanks for the comments.
