---
layout: post
title: Overview of Payment Services in Dynamics NAV 2009 R2
date: 2012-08-31 12:48
author: suvidha shashikumar
comments: true
categories: [Articles, Dynamics NAV, NAV 2009, Payment Services, Suvidha Shashikumar, Uncategorized]
---
<p><a title="Suvidha Shashikumar - Click for blog homepage"><img border="0" hspace="10" alt="Suvidha Shashikumar - Click for blog homepage" align="right" src="https://microsofttpd.github.io/assets/1452.sshashi.jpg" original-url="https://microsofttpd.github.io/assets/1452.sshashi.jpg" width="80" height="95" /></a>One of the most attractive features in NAV 2009 R2 release is the Payment services integration. Payment service integration is an out of the box feature in NAV 2009 R2 which can be easily setup to start accepting credit cards and debit cards for the payment transactions from customers. To help facilitate this feature, Microsoft provides online service for Dynamics ERP customers for free.</p>
<p>This integration allows users to accept credit/debit cards from sales orders, sales invoices and cash receipts. Refund to the customer&rsquo;s credit card can be done from existing credit memo functionality (against existing credit card transaction only).</p>
<p>Following credit card payments terminologies are important to remember:</p>
<ul>
<li>
<div style="padding-left: 30px;"><strong>Authorize:</strong> Ensure Credit Availability before accepting a sale.</div>
</li>
<li>
<div style="padding-left: 30px;"><strong>Capture:</strong> Actually deduct money from Credit Card and automatically create and apply Payment in NAV.</div>
</li>
<li>
<div style="padding-left: 30px;"><strong>Refund:</strong> Refund money to the customer&rsquo;s credit card using existing credit memo functionality against existing credit card transaction.</div>
</li>
<li>
<div style="padding-left: 30px;"><strong>Void:</strong> Against existing authorization.&nbsp;</div>
</li>
</ul>
<p><strong>HOW IT WORKS:</strong><br />Customer &ldquo;ABC&rdquo; places an order for Bicycle with Suzie-the sales order processor at Cronus International Limited and &ldquo;ABC&rdquo; wishes to pay for this order using their credit card.</p>
<p><strong>Steps followed by Suzie:</strong></p>
<ol>
<li>
<div style="padding-left: 30px;">Collects credit card details from &ldquo;ABC&rdquo; and stores them in customer credit card details page in Dynamics NAV (Customer card--&gt; Customer (button)--&gt; Credit cards).</div>
</li>
<li>
<div style="padding-left: 30px;">Suzie creates a sales order for &ldquo;ABC&rdquo; with customer details, the payment method meant for credit card payments and credit card number in the header and Bicycle details in the line.</div>
</li>
<li>
<div style="padding-left: 30px;">Once the sales order is ready, the credit card can be validated by Authorize functionality (Functions--&gt;Authorize).</div>
</li>
<li>
<div style="padding-left: 30px;">Once the credit card is authorized, the sales order can be posted and during this posting, capture of amount against the credit card will happen.&nbsp;</div>
</li>
<li>
<div style="padding-left: 30px;">Both authorize and capture related transactions will be stored at credit card transaction log entries (customer card&nbsp;--&gt; Customer (button)&nbsp;--&gt; credit card transaction log entries).</div>
</li>
</ol>
<p>Similarly, the credit cards can be accepted in a sales invoice, cash receipt and credit memo (Refund against an existing credit card transaction).<br />Also, a customer can have multiple credit cards stored against their account in NAV.&nbsp;</p>
<p>For this feature to be working, there are 2 parts to the <strong>setup</strong>:&nbsp;</p>
<p><strong>Setup Within Dynamics NAV</strong></p>
<p>1.&nbsp;The <strong>payment methods</strong> page in NAV 2009 R2 has a new field called <strong>Payment Processor</strong>. A new payment method is required with &ldquo;Dynamics Online&rdquo; option selected in this field. Also, <strong>Bal. Account Type</strong> should be &ldquo;Bank Account&rdquo; (Self-explanatory!!) and of course <strong>Bal. Account No.</strong> should contain the bank account code which is used for credit/debit card transactions. This new payment method should be used for online payment service related transactions. More details <a title="here" href="http://msdn.microsoft.com/en-us/library/gg502459.aspx" target="_blank">here</a></p>
<p>2.&nbsp;Payment services setup page is used to setup few conditions within Dynamics NAV. More details <a title="here" href="http://msdn.microsoft.com/en-us/library/gg502506" target="_blank">here</a></p>
<p>3.&nbsp;The credit card detail of the customer has to be stored manually against a customer code in the new DO payment credit card table. i.e., this functionality does not support accepting the credit card details during the payment transaction (swiping of credit card or customer entering the credit card online directly is not available). Credit card setup explained <a title="here" href="http://msdn.microsoft.com/en-us/library/gg502498" target="_blank">here</a></p>
<p>4.&nbsp;LCY code on the General Ledger Setup page has to be setup correctly to handle credit card payments. For list of valid currency codes <a title="click here" href="http://msdn.microsoft.com/en-us/library/gg502492" target="_blank">click here</a></p>
<p><strong>Setup Outside Dynamics NAV: </strong></p>
<p>1.&nbsp;This part requires signing up an account online with Payment services for Microsoft Dynamics ERP using live ID. This can be ideally initiated from <strong>Payment services connection setup</strong> form (the classic client form&nbsp;has to be used for this setup due to proxy related issue).</p>
<p>This process requires:</p>
<p style="padding-left: 30px;">a)&nbsp;Basic account information<br />b)&nbsp;Signing up for a payment service and enabling the same.<br />c)&nbsp;Link the payment service to the NAV database.<br />d)&nbsp;Apply to payment providers.<br />e)&nbsp;Activate the provider account.<br />f)&nbsp;Configure payment methods.</p>
<p>The last 3 points can be ignored in case of demo setup for payment services with Dynamics NAV.<br />This setup is explained in the document available for download <a title="here" href="https://mbs.microsoft.com/partnersource/deployment/documentation/whitepapers/MSDNAV2009R2Provpaymnt" target="_blank">here</a>. (PartnerSource access required!).</p>
<p><strong>Benefits:</strong><br />1.&nbsp;This feature is provided out of the box in NAV 2009 R2 and requires minimal setup.<br />2.&nbsp;All major credit cards and debit cards can be accepted for payments from customers in secure way (SSL).<br />3.&nbsp;The service is hosted online by Microsoft for all the Dynamics ERP customers for free :)<br />4.&nbsp;This feature authorizes card, captures payment automatically and also refunds against a debit/credit card in case of returns from customer.<br />5.&nbsp;The credit card number is encrypted and stored in dynamics NAV database, ensuring the security of the data.</p>
<p><strong>Limitations:</strong><br />1.&nbsp;Unfortunately, this feature is now available only in USA and Canada, but of course it is expected to be released in other parts of the world as well:).<br />2.&nbsp;The list of <a title="payment providers" href="http://www.dynamicsonline.com/OnlinePaymentsSellPages/SellPage.aspx?ActiveIndex=2" target="_blank">payment providers</a> is limited to few as of now (Although we have almost all major payment providers), but this is likely to expand.<br />3.&nbsp;The credit card details have to be entered manually into the system i.e., swiping of the cards or customers&rsquo; entering the card details online is not available.<br />4.&nbsp;As of now, types of cards accepted are VISA, MASTER CARD, AMERICAN EXPRESS and DISCOVER.</p>
