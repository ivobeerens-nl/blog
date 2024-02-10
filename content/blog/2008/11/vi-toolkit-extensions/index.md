---
title: "VI Toolkit Extensions"
date: "2008-11-04T12:57:17.000Z"
categories: 
  - "powershell"
  - "vi-toolkit"
  - "vmware"
tags: 
  - "power"
  - "vi-toolkit"
  - "vmware"
---

Today I tested the VI Toolkit extensions.  The VI Toolkit extensions are cmdlets that makes your life easier. Here are some functions of what the cmdlets can do:

[![6a00d8341c328153ef01053565af86970b-800wi](images/6a00d8341c328153ef01053565af86970b-800wi-thumb.png)](https://www.ivobeerens.nl/wp-content/uploads/2008/11/6a00d8341c328153ef01053565af86970b-800wi.png)

The VI toolkit extensions require PowerShell V2 CTP 2 and the VI Toolkit. The VI toolkit extension can be downloaded @ [http://www.codeplex.com/vitoolkitextensions](http://www.codeplex.com/vitoolkitextensions)

Example:

**list all VMs by name and list the size of the snapshots**

\- Open VI-toolkit

\- Connect-VIserver VCservername

\- To add the extension, use the following command:

> Add-Module "D:\\Scripts\\viToolkitExtensions.psm1"

> Get-VM | Get-TkeSnapshotExtended | select Name, VM, SizeMB

Output:

[![image](images/image-thumb.png)](https://www.ivobeerens.nl/wp-content/uploads/2008/11/image.png)
