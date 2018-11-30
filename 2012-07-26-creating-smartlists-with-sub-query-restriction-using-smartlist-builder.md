---
layout: post
title: Creating Smartlists with Sub Query Restriction using Smartlist Builder
date: 2012-07-26 12:02
author: sivakumar v
comments: true
categories: [Articles, Dynamics GP, Sivakumar Venkataraman, Smartlist Builder, Uncategorized]
---
<p style="text-align: left;"><a title="Sivakumar Venkataraman - Click for blog homepage"><img border="0" hspace="10" alt="Sivakumar Venkataraman - Click for blog homepage" align="right" src="https://microsofttpd.github.io/assets/0871.sivav.jpg" width="80" height="95" /></a>Smartlist Builder is a great tool to create custom smartlists. We can create smartlists using Dynamics GP tables (or) using SQL objects. However, there have been many requests from customers and partners to&nbsp;retrieve the data from smartlist using a sub query filter. An example of such a request is to pull out all payables transactions with the complete distributions, where specific expense accounts are used. Assuming a<br />voucher has the following distributions.&nbsp;&nbsp;</p>
<table border="1" cellspacing="0" cellpadding="0">
<tbody>
<tr>
<td valign="top" width="160">
<p><b>Account Number</b></p>
</td>
<td valign="top" width="160">
<p><b>Description</b></p>
</td>
<td valign="top" width="160">
<p><b>Debit</b></p>
</td>
<td valign="top" width="160">
<p><b>Credit</b></p>
</td>
</tr>
<tr>
<td valign="top" width="160">
<p>000-2100-00</p>
</td>
<td valign="top" width="160">
<p>Accounts Payable</p>
</td>
<td valign="top" width="160">
<p>$0.00</p>
</td>
<td valign="top" width="160">
<p>$1500.00</p>
</td>
</tr>
<tr>
<td valign="top" width="160">
<p>000-6010-00</p>
</td>
<td valign="top" width="160">
<p>Advertising Expenses</p>
</td>
<td valign="top" width="160">
<p>$1400.00</p>
</td>
<td valign="top" width="160">
<p>$0.00</p>
</td>
</tr>
<tr>
<td valign="top" width="160">
<p>000-6630-00</p>
</td>
<td valign="top" width="160">
<p>Suspense Expenses</p>
</td>
<td valign="top" width="160">
<p>$100.00</p>
</td>
<td valign="top" width="160">
<p>$0.00</p>
</td>
</tr>
</tbody>
</table>
<p>The request is to extract the specific voucher and all its distribution lines if the miscellaneous expenses account was used. This is ideally to analyze the complete distribution in the voucher so that the need for the suspense account can be analyzed. Ideally, for such scenarios, a&nbsp; SQL query would be the best option. The SQL query typically looks as what is shown below.</p>
<div class="legend"><strong>Code Example</strong></div>
<div style="margin: 20px 0px 10px; overflow: auto; width: 97.5%; cursor: text; max-height: 200px; line-height: 12pt; background-color: #f4f4f4; font-size: 8pt; font-family: 'Courier New', courier, consolas, monospace; white-space: nowrap; border: gray 1px solid; padding: 4px;" class="code">
<pre>SELECT  * FROM   
dbo.PM30600
WHERE   VCHRNMBR IN ( SELECT    VCHRNMBR
                      FROM      dbo.PM30600
                                WHERE     DSTINDX IN
( 167, 256 ) )
                AND
dbo.PM30600.DOCTYPE = 1
ORDER BY dbo.PM30600.VCHRNMBR
</pre>
<pre>&nbsp;</pre>
</div>
<p>We can make use of the &ldquo;Is Equal To One of List&rdquo; option and provide a subset of vouchers which need to be returned, but it is not the efficient method of achieving the same, since the filter in the SLB definition needs to be changed every time we run the query to get the appropriate results, which does not make sense. This article explores more into how this functionality can be achieved using Smartlist Builder.</p>
<p>First create an Equals JOIN (there is not Inner Join option in SLB, use Equals) between the PM Distribution History File and the PM Paid Transaction History File with the Voucher Number and Document Type. Then add a restriction on the Distribution Account to be one of the following accounts as seen in the screen shot below.</p>
<ul>
<li>000-6630-00</li>
<li>300-6530-00</li>
</ul>
<p><b><i><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/0216.1.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/0216.1.png"><img border="0" alt="" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/0216.1.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/0216.1.png" /></a></i></b></p>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3201.2.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3201.2.png"><img border="0" alt="" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/3201.2.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/3201.2.png" /></a></p>
<p><b><i>Note:</i></b><i> The restriction has to be applied on the distribution table which has an inner join with the transaction history table and NOT on the one which has the left outer join with the transaction history table.</i></p>
<p>Now create a LEFT OUTER JOIN between the PM Transaction History File and the PM Distribution History File with the Voucher Number and the Document Type. Display the distribution details (Account Number, Debit Amount and Credit Amount) from this distribution table. &nbsp;Click on Options and select the option Summary Smartlist and change the Summary Type for the following fields as explained below.</p>
<ul>
<li>PM Paid Transaction History File &ndash; Voucher Number &nbsp;&ndash; Group By</li>
<li>PM Paid Transaction History File &ndash; Vendor ID &ndash; Group By</li>
<li>PM Paid Transaction History File &ndash; Document Type &ndash; Group By</li>
<li>PM Paid Transaction History File &ndash; Document Date &ndash; Group By&nbsp;</li>
<li>PM Paid Transaction History File &ndash; Document Number &ndash; Group By</li>
<li>PM Transaction Distribution History (3rd table shown above) &ndash; Voucher Number &ndash; Group By</li>
<li>PM Transaction Distribution History (3rd table&nbsp; shown above) &ndash; Distribution Sequence Number &ndash; Group By</li>
<li>PM Transaction Distribution History (3rd table&nbsp; shown above) &ndash; Distribution Account Index &ndash; Group By</li>
<li>PM Transaction Distribution History (3rd table shown above) &ndash; Distribution Type &ndash; Group By</li>
<li>PM Paid Transaction History File &ndash; Document Amount &ndash; Average</li>
<li>PM Transaction Distribution History (3rd table&nbsp; shown above) &ndash; Debit Amount &ndash; Average</li>
<li>PM Transaction Distribution History (3rd table shown above) &ndash; Originating Debit Amount &ndash; Average</li>
<li>PM Transaction Distribution History (3rd table shown above) &ndash; Credit Amount &ndash; Average</li>
<li>PM Transaction Distribution History (3rd table shown above) &ndash; Originating Credit Amount &ndash; Average</li>
</ul>
<p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/6470.3.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/6470.3.png"><img border="0" alt="" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/95/09/6470.3.png" original-url="http://blogs.technet.com/resized-image.ashx/__size/550x0/__key/communityserver-blogs-components-weblogfiles/00-00-00-95-09/6470.3.png" /></a></p>
<p>This provides the same results that we would have obtained using the SQL query provided above.</p>
