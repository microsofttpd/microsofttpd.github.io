---
layout: post
title: Posting Levels in Dynamics GP – A Review
date: 2012-08-24 13:19
author: sivakumar v
comments: true
categories: [Articles, Detailed, Dynamics GP, GL Accounts, Posting Levels, Sivakumar Venkataraman, Summary, Uncategorized]
---
<p><a title="Sivakumar Venkataraman - Click for blog homepage"><img width="80" height="95" align="right" alt="Sivakumar Venkataraman - Click for blog homepage" src="https://microsofttpd.github.io/assets/0871.sivav.jpg" border="0" hspace="10" /></a>There have been many questions from many customers on the various levels of postings to the General Ledger accounts that are available in Dynamics GP. This article explains the posting levels with its advantages and disadvantages.</p>
<p>The level of posting to the GL accounts is determined from couple of setups that work hand in hand in Dynamics GP. The initial setup is to define the level of postings for various accounts in the Account Maintenance window from <em>Cards &gt;&gt; Financials &gt;&gt; Accounts</em> as illustrated below.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8741.1.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8741.1.png"><img alt="" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8741.1.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8741.1.png" border="0" /></a>&nbsp;<a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2746.2.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2746.2.png"><img alt="" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/2746.2.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/200x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/2746.2.png" border="0" /></a><br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <br />We can specify the levels of posting from the various series into the General Ledger module. The various options available for posting levels are</p>
<ul>
<li>Detail</li>
<li>Summary</li>
</ul>
<p>Once this has been setup, we need to define the level of posting for various transactions in various modules in the Posting Setup window from Microsoft Dynamics GP &gt;&gt; Tools &gt;&gt; Setup &gt;&gt; Posting &gt;&gt; Posting as illustrated below.</p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8400.3.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8400.3.png"><img alt="" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/8400.3.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/400x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/8400.3.png" border="0" /></a><br />&nbsp;<br />So for the purpose of this case study, let us create a couple of receivable invoices with the distributions explained below and save them in a batch called RECVINV.</p>
<p><strong>Invoice #1</strong></p>
<table align="left" border="0">
<tbody>
<tr>
<td><strong>Invoice Number</strong></td>
<td><strong>Account Number</strong></td>
<td><strong>Type</strong></td>
<td><strong>Debit Amount</strong></td>
<td><strong>Credit Amount</strong></td>
</tr>
<tr>
<td>INV0001</td>
<td>000-1200-00</td>
<td>RECV</td>
<td>$500</td>
<td>$0</td>
</tr>
<tr>
<td>INV0001</td>
<td>000-4100-00</td>
<td>SALES</td>
<td>$0</td>
<td>$500</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p><strong>Invoice #2</strong></p>
<table align="left" border="0">
<tbody>
<tr>
<td><strong>Invoice Number</strong></td>
<td><strong>Account Number</strong></td>
<td><strong>Type</strong></td>
<td><strong>Debit Amount</strong></td>
<td><strong>Credit Amount</strong></td>
</tr>
<tr>
<td>INV0002</td>
<td>000-1200-00</td>
<td>RECV</td>
<td>$700</td>
<td>$0</td>
</tr>
<tr>
<td>INV0002</td>
<td>000-4100-00</td>
<td>SALES</td>
<td>$0</td>
<td>$700</td>
</tr>
</tbody>
</table>
<p><br />&nbsp;</p>
<p>&nbsp;</p>
<p>Now, in the Posting Setup window, if we select the option to create one journal entry per transaction, posting will always be done at a detailed level (irrespective of the setting specified in the Account Maintenance window) (i.e.) There will be a one-to-one match between the distribution lines in the journal entry and the distribution that we had noted in the transaction posted in the sub ledgers.</p>
<p>So when the above batch RECVINV is posted in the Receivables module, there will be 2 journal entries created with the distributions explained below.</p>
<p><strong>Journal Entry #1</strong></p>
<table align="left" border="0">
<tbody>
<tr>
<td><strong>Journal Entry No</strong></td>
<td><strong>Account Number</strong></td>
<td><strong>Debit Amount</strong></td>
<td><strong>Credit Amount</strong></td>
</tr>
<tr>
<td>12345</td>
<td>000-1200-00</td>
<td>$500</td>
<td>$0</td>
</tr>
<tr>
<td>12345</td>
<td>000-4100-00</td>
<td>$0</td>
<td>$500</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p><strong>Journal Entry #2</strong></p>
<table align="left" border="0">
<tbody>
<tr>
<td><strong>Journal Entry No</strong></td>
<td><strong>Account Number</strong></td>
<td><strong>Debit Amount</strong></td>
<td><strong>Credit Amount</strong></td>
</tr>
<tr>
<td>12346</td>
<td>000-1200-00</td>
<td>$700</td>
<td>$0</td>
</tr>
<tr>
<td>12346</td>
<td>000-4100-00</td>
<td>$0</td>
<td>$700</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>However in the posting setup, if we specify the option to create a journal entry per batch, we have two levels of roll ups that are available when journal entries are created when the sub ledger transactions are posted.<br />If the &ldquo;Use Account Settings&rdquo; option is unchecked, then when a batch of transactions is posted from the sub ledger module, the system creates one journal entry for all transactions posted in the sub ledger batch and the amounts gets rolled up for all the GL accounts in the two invoices which are posted as illustrated below.</p>
<p><strong>Journal Entry #1</strong></p>
<table align="left" border="0">
<tbody>
<tr>
<td><strong>Journal Entry No</strong></td>
<td><strong>Account Number</strong></td>
<td><strong>Debit Amount</strong></td>
<td><strong>Credit Amount</strong></td>
</tr>
<tr>
<td>12345</td>
<td>000-1200-00</td>
<td>$1200</td>
<td>$0</td>
</tr>
<tr>
<td>12345</td>
<td>000-4100-00</td>
<td>$0</td>
<td>$1200</td>
</tr>
</tbody>
</table>
<p><br />&nbsp;&nbsp;&nbsp;</p>
<p>&nbsp;</p>
<p>Now let us update the account 000-1200-00 to post at a Summary Level in the Sales Series in the Account Maintenance window. Let us also setup the account 000-4100-00 to post in detail in the Sales Series in the Account Maintenance window.</p>
<p>If the &ldquo;<em>Use Account Settings</em>&rdquo; option is checked, then a batch of transactions posted from the sub ledger module will create one journal entry for all transactions posted in the sub ledger batch and the distribution amounts are rolled based on the posting levels for the accounts that are defined in the Account Maintenance window.</p>
<p>So in the same case study example above, if the batch was posted in the Receivables module, there will be one journal entry created with the distributions illustrated below.</p>
<p><strong>Journal Entry #1</strong></p>
<table align="left" border="0">
<tbody>
<tr>
<td><strong>Journal Entry No</strong></td>
<td><strong>Account Number</strong></td>
<td><strong>Debit Amount</strong></td>
<td><strong>Credit Amount</strong></td>
</tr>
<tr>
<td>12345</td>
<td>000-1200-00</td>
<td>$1200</td>
<td>$0</td>
</tr>
<tr>
<td>12345</td>
<td>000-4100-00</td>
<td>$0</td>
<td>$500</td>
</tr>
<tr>
<td>12345</td>
<td>000-4100-00</td>
<td>$0</td>
<td>$700</td>
</tr>
</tbody>
</table>
<p><br /><br />&nbsp;</p>
<p>&nbsp;</p>
<p><strong>Note:</strong> Keep in mind that the various levels of postings will also be in effect only when we perform a batch posting in the sub ledger. If the posting is done at a transaction level, the system will always post in detail to the General Ledger (irrespective if the settings in the Account Maintenance window and the Posting Setup window for the specific sub ledger transaction).</p>
