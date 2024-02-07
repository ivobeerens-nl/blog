---
author: Ivo Beerens
categories:
- vcenter
- vSphere
date: "2012-01-06T11:02:51Z"
guid: http://www.ivobeerens.nl/?p=1227
id: 1227
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- vCenter
- vSphere
title: VMware vCenter 4 and MS SQL Express 2008 R2 bug
url: /2012/01/06/vmware-vcenter-4-and-ms-sql-express-2008-r2-bug/
---

<span style="color: #000000;">When looking for performance data in vCenter 4.1 from the past week, month or year, I got the message “Performance data is currently not available for this entry”. Only real time data is visible in vSphere client.</span>

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/01/image_thumb.png "image")</span>](http://localhost/wp-content/uploads/2012/01/image.png)

<span style="color: #000000;">In the vCenter Service Status the warning “Performance statistics rollup from Past Day to Past Week is not occurring in the database” appeared. </span>

[![image](http://localhost/wp-content/uploads/2012/01/image_thumb3.png "image")](http://localhost/wp-content/uploads/2012/01/image3.png)

<span style="color: #000000;">The vCenter server is installed on MS Windows 2008 R2 and uses vCenter server version 4.1 Update 2 Build 491557 with Microsoft SQL Server 2008 Express R2 64-bit. </span>

<span style="color: #000000;">When looking in the VMware Product Interoperability matrixes, it says is a supported configuration.</span>

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/01/image_thumb2.png "image")</span>](http://localhost/wp-content/uploads/2012/01/image2.png)

<span style="color: #000000;">Searching on the </span><span style="color: #000000;">[VMTN](http://communities.vmware.com/thread/308894?start=15&tstart=0) </span><span style="color: #000000;">I found more people who are experiencing this problem. The following </span><span style="color: #000000;">KB article</span><span style="color: #000000;"> says:</span>

> <span style="font-family: arial;"><span style="color: #000000; font-size: small;">To resolve this issue, migrate the SQL database to a full edition (32bit or 64bit) or a 32bit SQL Express edition. For more information on how to move the vCenter Server SQL database, see………..</span></span>

<span style="color: #000000;">For small environments this is not an option! When installing vCenter 4.1 Update 2, the MS SQL Express 2005 database is default installed. MS SQL Express 2005 is 32-bit application and you can have a maximum database size of 4GB. With MS SQL Server 2008 Express R2 64-bit you can have maximum database size of 10GB. </span>

<span style="color: #000000;">vCenter 5 installs by default MS SQL Server 2008 Express R2 64-bit and doesn’t have this bug. </span>

<span style="color: #000000;">The MS SQL Express database is only supported for test and small VMware environments (5 hosts and 50 VMs maximum). </span>

<span style="color: #000000;">So watch out when considering MS SQL Server 2008 Express R2 64-bit and vCenter 4!</span>
