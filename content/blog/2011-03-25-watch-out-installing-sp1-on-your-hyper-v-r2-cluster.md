---
author: Ivo Beerens
categories:
- Hyper-V
date: "2011-03-25T22:20:15Z"
guid: http://www.ivobeerens.nl/?p=816
id: 816
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hyper-v r2
title: Watch out installing SP1 on your Hyper-V R2 cluster
url: /2011/03/25/watch-out-installing-sp1-on-your-hyper-v-r2-cluster/
---

<font color="#000000"></font>

<font color="#000000">Yesterday I spoke a customer who has problems after applying Windows 2008 R2 SP1 on his 5 node Hyper-V cluster. When validating the storage on the cluster, the following error “disk with identifier “2ef8c0……” has a persistent reservation” is displayed on multiple cluster disks.</font>

**<font color="#000000"></font>**

**<font color="#000000">Update 27-04-2010:</font>**

<font color="#000000">**The problem can occur in the following scenario:**</font>

<font color="#000000">**– You configure a failover cluster that has three or more nodes that are running Windows Server 2008 R2 Service Pack 1 (SP1).   
– You have cluster disks that are configured in groups other than the Available Storage group or that are used for Cluster Shared Volumes (CSV).   
– These disks are online when you run the Validate SCSI Device Vital Product Data (VPD) test or the List Potential Cluster Disks storage validation test.**</font>

<font color="#000000">**In this scenario, the Validate SCSI Device Vital Product Data (VPD) test fails. Additionally, you receive an error message that resembles the following:** </font>

> <font color="#000000">**Failed to get SCSI page 83h VPD descriptors for cluster disk <number> from <node name> status 2**</font>

<font color="#000000"></font>

<font color="#000000">**The List Potential Cluster Disks storage validation test may display a warning message that resembles the following:**</font>

> <font color="#000000">**Disk with identifier <value> has a Persistent Reservation on it. The disk might be part of some other cluster. Removing the disk from validation set.**</font>

<font color="#000000"></font>

<font color="#000000">**A hotfix (KB 2531907) is now available that addresses the Win2008 R2 service pack 1 issue with Validate on a 3+ node cluster. You can find more information and the hotfix to download at the following link:** </font>[<font color="#000000">**KB2531907**</font>](http://support.microsoft.com/kb/2531907)<font color="#000000"></font>

<font color="#000000"><strike>My advice, do **not** install SP1 on your production Hyper-V cluster(s) till Microsoft has solution for this nasty problem!</strike> <strike>If you experience this problem watch and report in this </strike></font>[<font color="#000000"><strike>topic</strike></font>](http://social.technet.microsoft.com/Forums/en-US/winserverClustering/thread/e67026af-7f9b-4698-9ca7-11853431ed86)<font color="#000000"><strike>.</strike></font>

<font color="#000000"></font>

<font color="#000000">Topic information was found in this </font>[<font color="#000000">blog</font>](http://itinfras.blogspot.com/2011/03/be-careful-while-deploying-2008-r2-sp1.html)<font color="#000000">.</font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"> </font>

<font color="#000000"></font>
