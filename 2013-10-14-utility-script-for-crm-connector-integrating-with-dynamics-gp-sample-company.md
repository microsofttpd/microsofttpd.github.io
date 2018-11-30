---
layout: post
title: Utility Script for CRM Connector Integrating with Dynamics GP Sample Company
date: 2013-10-14 15:22
author: sivakumar v
comments: true
categories: [Articles, CRM Connector, Dynamics GP, Fabricam, Sample Company, Sivakumar Venkataraman, SQL Script, Uncategorized]
---
<p style="text-align: left;"><a title="Sivakumar Venkataraman - Click for blog homepage"><img src="https://microsofttpd.github.io/assets/0871.sivav.jpg" alt="Sivakumar Venkataraman - Click for blog homepage" width="80" height="95" align="right" border="0" hspace="10" /></a>This is an interesting script which I have decided to post in this article.</p>
<p>When we configure CRM Connector with Dynamics GP for the sample company (Fabricam, Inc.,), there is a known issue in the way the sample company data is structured.</p>
<p>As many of you would be aware of, the sample company data has a date stamp in the year 2017. Because of this, when the Connector maps are activated, the sample data gets integrated and the &ldquo;Check for data modified after&rdquo; gets updated to the date as per the date stamp, which will be a date in the year 2017.</p>
<p>And when we add any new records into the sample company, this data does not get integrated as the DEX_ROW_TS field (date stamp) for the new records will be the current date and the Connector integration ignores these records as it checks for data only added/modified after the date in the year 2017 as per the original sample data integration.</p>
<p>You can modify the &ldquo;Check for data modified after&rdquo; property for the integrations to the current date and time, but it will check for the data in the year 2017 and get updated back to 2017. This is because the sample company&rsquo;s data resides with the date stamp of 2017.</p>
<p>I have written a simple script which will update the DEX_ROW_TS in all Dynamics GP tables to the current date and time. This script can be run in both the system database and the company database.</p>
<p><strong>SQL Script for this purpose:</strong></p>
<p><em>DECLARE @TableName VARCHAR(15) </em><br /><em>DECLARE @DateStamp DATETIME</em><br /><em>DECLARE @SQLString VARCHAR(255)</em></p>
<p><em>SET @DateStamp = GETDATE()</em></p>
<p><em>DECLARE crTables CURSOR </em><br /><em>&nbsp;&nbsp;&nbsp; FOR </em><br /><em>&nbsp;&nbsp;&nbsp; select name from sys.objects where type = 'U' ORDER by name</em></p>
<p><em>OPEN crTables</em></p>
<p><em>FETCH NEXT FROM crTables INTO @TableName</em></p>
<p><em>WHILE @@FETCH_STATUS = 0 </em><br /><em>BEGIN </em><br />&nbsp;&nbsp;&nbsp; <br /><em>&nbsp;&nbsp;&nbsp; IF EXISTS (SELECT * FROM INFORMATION_SCHEMA.columns </em><br /><em>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; WHERE TABLE_NAME = @TableName </em><br /><em>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; AND COLUMN_NAME = 'DEX_ROW_TS') </em><br /><em>&nbsp;&nbsp;&nbsp; BEGIN</em><br />&nbsp;&nbsp;<br /><em>&nbsp;&nbsp;SET @SQLString = 'UPDATE dbo.' + LTRIM(RTRIM(@TableName)) + ' SET DEX_ROW_TS = ''' + CONVERT(VARCHAR(10), @DateStamp, 120) + ''''</em><br /><em>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; EXECUTE(@SQLString)</em></p>
<p><em>&nbsp;&nbsp;&nbsp; END </em><br /><em>&nbsp;&nbsp;&nbsp; FETCH NEXT FROM crTables INTO @TableName </em><br /><em>END</em></p>
<p><em>CLOSE crTables</em></p>
<p><em>DEALLOCATE crTables</em></p>
<p><strong>Note: </strong>Make sure you have a valid backup of the system and company databases before running this script.</p>
<p>I hope this script will be useful for all those who are trying to test CRM Connector for Dynamics GP using the sample company. I have attached this script at the end of the article.</p>
<p>Until next post!</p>
<p><strong>Attachments:</strong>&nbsp;<a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3731.paperclip.gif" original-url="http://blogs.technet.com/cfs-filesystemfile.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3731.paperclip.gif"><img style="max-height: 14px; max-width: 15px;" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3731.paperclip.gif" original-url="http://blogs.technet.com/cfs-filesystemfile.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3731.paperclip.gif" alt="" border="0" /></a><a title="MBS_CRMConnectorwithGP_DEXROWTSUpdate.zip" href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/attachments/7711.MBS_CRMConnectorwithGP_DEXROWTSUpdate.zip" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09-attachments/7711.MBS_CRMConnectorwithGP_DEXROWTSUpdate.zip" target="_blank">MBS_CRMConnectorwithGP_DEXROWTSUpdate.zip</a>&nbsp;</p>
