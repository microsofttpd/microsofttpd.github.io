---
layout: post
title: Management Reporter 2012 CU11 Company Integration with Microsoft Dynamics GP 2015
date: 2014-12-30 09:27
author: sivakumar v
comments: true
categories: [Articles, Company Integration, CU11, Dynamics GP 2015, Management Reporter 2012, Sivakumar Venkataraman, Uncategorized]
---
<p style="text-align:left;"><a title="Sivakumar Venkataraman - Click for blog homepage"><img border="0" hspace="10" alt="Sivakumar Venkataraman - Click for blog homepage" src="https://microsofttpd.github.io/assets/0871.sivav.jpg" width="80" align="right" height="95" /></a>I was testing out the new CU 11 for Management Reporter 2012 today with Dynamics GP 2015. After the installation and configuration, I was trying to enable the integration and I noticed that the option to add the companies to MR for the DataMart adaptor was missing in Management Reporter Configuration Console.</p>
<p>I realized that the set up was in Dynamics GP and I went to<strong> Tools &gt;&gt; Setup &gt;&gt; System &gt;&gt; Reporting Tools Setup</strong> and configured the MR Service location and clicked OK, hoping this will enable the companies into MR. However, it was not to be the case. After doing some research and checking with Ryan, I came to realize that there was an option in the Company Setup which needs to be turned on in order for the specific company to be integrated into Management Reporter.</p>
<p>To access this, you need to go to <strong>Tools &gt;&gt; Setup &gt;&gt; Company &gt;&gt; Company</strong>. Click on the Options button and you would see a new section called Management Reporter as shown below.</p>
<p><a href="https://microsofttpd.github.io/assets/companysetup_61DD62F1.png" original-url="https://microsofttpd.github.io/assets/companysetup_61DD62F1.png"><img title="companysetup" style="background-image:none;padding-top:0px;padding-left:0px;display:inline;padding-right:0px;border:0px;" border="0" alt="companysetup" src="https://microsofttpd.github.io/assets/companysetup_thumb_33866DF5.png" original-url="https://microsofttpd.github.io/assets/companysetup_thumb_33866DF5.png" width="438" height="510" /></a></p>
<p>We can enable the General Ledger Reporting and Analytical Accounting Reporting for a company inside Management Reporter from this section. Once the option is turned on, we can exit Configuration Console, open it again to see that this GP company has been integrated into Management Reporter.</p>
<p><a href="http://blogs.msdn.com/353868/ProfileUrlRedirect.ashx" target="_blank">Ryan</a> from the <a href="http://blogs.msdn.com/b/dynamics_financial_reporting/" target="_blank">Corporate Performance Management</a> team has blogged about this as well <a href="http://blogs.msdn.com/b/dynamics_financial_reporting/archive/2014/12/30/company-integration-with-microsoft-dynamics-gp-2015-cu-11-feature.aspx" target="_blank">here</a>.</p>
<p>I hope this helps&hellip;</p>
<p>Until next post!</p>
