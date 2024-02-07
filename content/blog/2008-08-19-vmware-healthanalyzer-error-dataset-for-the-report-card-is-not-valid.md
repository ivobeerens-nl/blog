---
author: Ivo Beerens
categories:
- Tools
- VMware
date: "2008-08-19T22:53:09Z"
guid: http://www.ivobeerens.nl/?p=96
id: 96
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Tools
- VMware
title: VMware HealthAnalyzer error &#8220;Dataset for the report card is not valid&#8221;.
url: /2008/08/19/vmware-healthanalyzer-error-dataset-for-the-report-card-is-not-valid/
---

VMware has released version 1.0 of VMware HealthAnalyzer. VMware HealthAnalyzer is an virtual appliance that collects and analyses the VMware configuration and analyses categorized by VMware Health check best practices. This tool can be uses by VMware consultants and VMware Authorized Consultant (VAC) partners.

The data can be exported to HTML and Microsoft Excel.

Some screenshots from VMware HealthAnalyzer:

[![image](http://localhost/wp-content/uploads/2008/08/image-thumb15.png)](http://localhost/wp-content/uploads/2008/08/image15.png)

The VMware HealthAnalyzer Appliance started

[![image](http://localhost/wp-content/uploads/2008/08/image-thumb16.png)](http://localhost/wp-content/uploads/2008/08/image16.png)

Report created

[![image](http://localhost/wp-content/uploads/2008/08/image-thumb17.png)](http://localhost/wp-content/uploads/2008/08/image17.png)

ESX hardware exported to Microsoft Excel.

[![image](http://localhost/wp-content/uploads/2008/08/image-thumb18.png)](http://localhost/wp-content/uploads/2008/08/image18.png)

Complete report exported to HTML.

I had problems using the VMware HealthAnalyzer on VMware VC 2.5 Update 2. <span lang="N">When i try to Create a new Report Card i’ve got the following message:</span>

Dataset for the report card is not valid. Dataset id=12 ; Datset File Name=/usr/share/ironman/capture/captureFiles/c20080817230624

VMware has confirmed there is a known issue, VMware HealthAnalyzer is not able to parse the version of the SDK correctly and released a fix. The are coming soon with a new version.
