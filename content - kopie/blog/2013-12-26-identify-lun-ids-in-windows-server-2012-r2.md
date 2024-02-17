---
author: Ivo Beerens
categories:
- Hyper-V
- windows server 2012
date: "2013-12-26T20:32:53Z"
guid: http://www.ivobeerens.nl/?p=2613
id: 2613
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- hyper-v
- windows server 2012
title: Identify LUN IDs in Windows Server 2012 R2
url: /2013/12/26/identify-lun-ids-in-windows-server-2012-r2/
---

During a Windows Server 2012 R2 Hyper-V implementation I needed to identify all the iSCSI disks (LUNs) presented by an EMC VNX SAN to the Hyper-v Failover cluster. Each presented iSCSI disk has a unique LUN ID. To View the LUN ID of a disk, you can use the **diskpart** command. Here are the steps to view the LUN ID of a disk:

- **View the disks**

<span style="font-family: 'Courier New';">list disk</span>

- **Select a disk**

<span style="font-family: 'Courier New';">select disk *<number>*</span>

[![image](http://localhost/wp-content/uploads/2013/12/image_thumb6.png "image")](http://localhost/wp-content/uploads/2013/12/image6.png)

- **View the LUN ID of the disk**

<span style="font-family: 'Courier New';">detail disk</span>

[![image](http://localhost/wp-content/uploads/2013/12/image_thumb7.png "image")](http://localhost/wp-content/uploads/2013/12/image7.png)

I didn’t find a PowerShell command to view the LUN IDs. You can create a PowerShell script that uses Diskpart to view all the disks and the corresponding LUN IDs.
