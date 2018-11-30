---
layout: post
title: Using Resco MobileCRM Woodford Solution for Configuring Field Service Mobile App
date: 2016-11-07 22:32
author: sivakumar v
comments: true
categories: [CRM Online, Dynamics CRM, Field Service, Microsoft Dynamics, MobileCRM, Resco, Sivakumar Venkataraman, Woodford]
---
<a title="Sivakumar Venkataraman - Click for blog homepage"><img src="https://microsofttpd.github.io/assets/0871.sivav.jpg" alt="Sivakumar Venkataraman - Click for blog homepage" align="right" hspace="10" height="95" border="0" width="80" /></a>I was recently working on a Field Service functionality demo, where I had to demonstrate the Field Service mobile app, with additional Field Service entities like Work Orders, Agreements and Bookable Resources to be set up using the mobile device.

As we needed the <strong>Resco MobileCRM Woodford Solution</strong> to be deployed in CRM Online, I downloaded the trial solution from the link below.

<a target="_blank" href="https://www.microsoft.com/en-us/dynamics/crm-customer-center/install-the-field-service-mobile-app.aspx#bkmk_step1">https://www.microsoft.com/en-us/dynamics/crm-customer-center/install-the-field-service-mobile-app.aspx#bkmk_step1</a>

Once downloading and installing this Solution for Dynamics CRM 2016 Online Update 1, I tried to go to Settings &gt;&gt; MobileCRM &gt;&gt; Woodford and access the MobileCRM Woodford setting.

It immediately promoted me with an error as shown below.

<a href="https://microsofttpd.github.io/assets/2016-11-08_034905.png"><img class="alignnone size-full wp-image-5535" alt="2016-11-08_034905" src="https://microsofttpd.github.io/assets/2016-11-08_034905.png" height="321" width="536" /></a>

Ideally the system should prompt you with a screenshot to increase the isolated storage for Silverlight as shown below.

<a href="https://microsofttpd.github.io/assets/Increase-Quota.png"><img class="alignnone size-full wp-image-5545" alt="increase-quota" src="https://microsofttpd.github.io/assets/Increase-Quota.png" height="251" width="429" /></a>

However, I was getting the same error message irrespective of the browser used.
<blockquote><strong>On doing some troubleshooting, I was running the browser in InPrivate mode and I realized that this setting was causing the issue. </strong></blockquote>
I tried to run the browser in the normal mode, and I was able to set the isolated storage setting properly and go ahead with configuring the Field Service Mobile app using the settings as explained in the article below.

<a target="_blank" href="https://www.microsoft.com/en-us/dynamics/crm-customer-center/install-the-field-service-mobile-app.aspx">https://www.microsoft.com/en-us/dynamics/crm-customer-center/install-the-field-service-mobile-app.aspx</a>

Hope this helps.
