---
layout: post
title: Update Rollup 14 for Microsoft Dynamics CRM 2011 is available!
date: 2013-07-12 02:53
author: sivakumar v
comments: true
categories: [Articles, Dynamics CRM 2011, Sivakumar Venkataraman, Uncategorized, Update Rollup, UR14]
---
<p style="text-align: left;"><a title="Sivakumar Venkataraman - Click for blog homepage"><img src="https://microsofttpd.github.io/assets/0871.sivav.jpg" alt="Sivakumar Venkataraman - Click for blog homepage" width="80" height="95" align="right" border="0" hspace="10" /></a>Update Rollup 14 for Microsoft Dynamics CRM 2011 is available. This article describes the hotfixes and updates that are included in this update rollup. This rollup is available for all languages that are supported by Microsoft Dynamics CRM 2011.</p>
<p><strong>Build number and file names for this update rollup</strong></p>
<table id="MT3" class="table" cellspacing="0">
<tbody>
<tr><th style="text-align: left;"><strong>Rollup package</strong></th><th>Build number</th><th><strong>File name (32-bit versions)</strong></th><th><strong>File name (64-bit versions)</strong></th></tr>
<tr>
<td>Microsoft Dynamics CRM 2011 Server</td>
<td>5.0. 9690.3557</td>
<td>Not applicable</td>
<td>CRM2011-Server-KB2849744-<var>LangID</var>-amd64.exe</td>
</tr>
<tr>
<td>Microsoft Dynamics CRM 2011 for Microsoft Office Outlook</td>
<td>5.0. 9690.3557</td>
<td>CRM2011-Client-KB2849744-<var>LangID</var>-i386.exe</td>
<td>CRM2011-Client-KB2849744-<var>LangID</var>-amd64.exe</td>
</tr>
<tr>
<td>Microsoft Dynamics CRM 2011 E-mail Router</td>
<td>5.0. 9690.3557</td>
<td>CRM2011-Router-KB2849744-<var>LangID</var>-i386.exe</td>
<td>CRM2011-Router-KB2849744-<var>LangID</var>-amd64.exe</td>
</tr>
<tr>
<td>Microsoft Dynamics CRM 2011 Report Authoring Extension</td>
<td>5.0. 9690.3557</td>
<td>CRM2011-Bids-KB2849744-<var>LangID</var>-i386.exe</td>
<td>Not applicable</td>
</tr>
<tr>
<td>Microsoft Dynamics CRM 2011 Language Pack</td>
<td>5.0. 9690.3557</td>
<td>CRM2011-Mui-KB2849744-<var>LangID</var>-i386.exe</td>
<td>CRM2011-Mui-KB2849744-<var>LangID</var>-amd64.exe</td>
</tr>
<tr>
<td>Microsoft Dynamics CRM 2011 Reporting Extensions</td>
<td>5.0. 9690.3557</td>
<td>Not applicable</td>
<td>CRM2011-Srs-KB2849744-<var>LangID</var>-amd64.3exe</td>
</tr>
</tbody>
</table>
<p><span>Update Rollup 14 for Microsoft Dynamics CRM 2011 will be available for on-premises customers in July 2013.&nbsp;</span><br /><br /><span>The following file is available for download from the Microsoft Download Center:</span></p>
<p>&nbsp;<img class="graphic" title="Download" src="http://support.microsoft.com/library/images/support/kbgraphics/public/EN-US/Download.gif" alt="Download" /><a title="Update Rollup 14 for Microsoft Dynamics CRM 2011" href="http://www.microsoft.com/downloads/details.aspx?FamilyID=a09fc910-94d9-46d1-b5a7-9a3c90b3cdc3" target="_blank">Download the 2849744 package now.</a>&nbsp;</p>
<div class="kb_nowrapper">
<div class="kb_nowrapper"><span>Update Rollup 14 resolves the following issues:</span>
<ul>
<li>Better performance around User and Team caching. For example, a user is a member of 15,000 teams. You login as this user and it takes a long time to cache all the data. If you login as another user, you see the same problem due to clearing the cache.&nbsp;</li>
<li>"Show Selected Views" does not work in CRM Dashboard.</li>
<li>Description field in activity views shows HTML style information.</li>
<li>Description field and notes are not displayed correctly during Print Preview after Update Rollup 12.</li>
<li>When you perform a Quick Find search in Outlook, the columns shown in the view are the intersection of the columns from the previous view that was shown in Outlook and the Quick Find view definition. This differs from what you see when you do a search in the web client. After the search is run, no columns are displayed because the specific column is not included in the Quick Find view.</li>
<li>WRPC token is missing when you use SharePoint Integration.</li>
<li>Adding a mail template in CRM after Update Rollup 12 causes errors.</li>
<li>Rich Text Editor errors occur when you paste content during creation of mail merge templates in CRM 2011 online.</li>
<li>My Team Members' Activities view displays incorrect results through CRM for Outlook client.</li>
<li><strong>AddressBookMaterializedViewsEnabled</strong>&nbsp;triggers a crash if entity does not have an email address.</li>
<li>Outlook folders are filtered only per the user&rsquo;s security, and does not take into account the security of the team the user is a part of.&nbsp;</li>
<li>SQL CE&nbsp;connections in 32-bit versions of the Microsoft Dynamics CRM 2011 Client for Outlook are not being released.</li>
<li>Memory errors in 32-bit CRM for Outlook when you go offline.</li>
<li>Templates are applied to distributed campaign email messages despite being deselected.</li>
<li>Formatting exceptions occur during data import.</li>
<li>Microsoft Dynamics CRM Reporting Extensions Data connector platform traces are not written when SSRS is on a separate computer from CRM.</li>
<li>Double quotation marks are changed to single quotation marks in KB articles.</li>
<li>When&nbsp;<strong>OverrideTrackInCrmBehaviour</strong>&nbsp;is enabled, you can't untrack email in CRM Outlook Client.</li>
<li>"Show only my records" in lookup dialog box doesn't always show just my records.</li>
<li>When you click&nbsp;<strong class="uiterm">View existing record in CRM</strong>&nbsp;in the Outlook client, nothing happens.</li>
<li>Errors occur when you send direct email in CRM outlook client while you're offline.</li>
<li>Sum of currency type field displays an incorrect currency symbol.</li>
<li>Outlook Quick Find displays Filter Criteria incorrectly after Update Rollup 12 is installed.</li>
<li>User can publish articles without the&nbsp;<strong>Publish article</strong>&nbsp;permission.</li>
<li>Email router stops processing email messages after it encounters a message that does not have a&nbsp;<strong class="uiterm">From</strong>&nbsp;field value.</li>
<li>Printer prompts for 8.3" x 11" paper when you print a report that was created in the report wizard.</li>
<li>Deleting entity triggers&nbsp;<strong>System.Array.Copy throws ArrayTypeMismatchException</strong>.</li>
<li>Base64 attributes are returned as&nbsp;<strong>MemoAttributeMetadata</strong>&nbsp;instead of as&nbsp;<strong>StringAttributeMetadata</strong>.</li>
<li>Excel sheet name isn't shown correctly on Update Rollup 12 when Advanced Find results are exported to Excel.</li>
<li>Microsoft CRM ribbon disappears in Outlook 2007 clients.</li>
<li>Process with condition on email recipient fails if recipient is unresolved.</li>
<li>Tasks tab is blank in the Synchronizing dialog box when you go offline.</li>
<li>Updating individual occurrences of a Recurrence Meeting breaks recurrence.</li>
<li>Outlook client crashes when you try to add email activity to order from outlook client.</li>
<li>"Error in LoadSiteWideSettings" error when you start Deployment Manager.</li>
</ul>
<div>I hope this helps the community. Happy Downloading!</div>
<div>Until next post!</div>
</div>
</div>
