---
author: Ivo Beerens
categories:
- Powershell
- VI Toolkit
- VMware
date: "2008-11-04T14:57:17Z"
guid: http://www.ivobeerens.nl/?p=141
id: 141
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- power
- VI Toolkit
- VMware
title: VI Toolkit Extensions
url: /2008/11/04/vi-toolkit-extensions/
---

Today I tested the VI Toolkit extensions. The VI Toolkit extensions are cmdlets that makes your life easier. Here are some functions of what the cmdlets can do:

[![6a00d8341c328153ef01053565af86970b-800wi](http://localhost/wp-content/uploads/2008/11/6a00d8341c328153ef01053565af86970b-800wi-thumb.png)](http://localhost/wp-content/uploads/2008/11/6a00d8341c328153ef01053565af86970b-800wi.png)

The VI toolkit extensions require PowerShell V2 CTP 2 and the VI Toolkit. The VI toolkit extension can be downloaded @ <http://www.codeplex.com/vitoolkitextensions>

Example:

**list all VMs by name and list the size of the snapshots**

– Open VI-toolkit

– Connect-VIserver VCservername

– To add the extension, use the following command:

> Add-Module “D:\\Scripts\\viToolkitExtensions.psm1”

> Get-VM | Get-TkeSnapshotExtended | select Name, VM, SizeMB

<span style="color: #777777;">Output:</span>

[![image](http://localhost/wp-content/uploads/2008/11/image-thumb.png)](http://localhost/wp-content/uploads/2008/11/image.png)
