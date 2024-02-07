---
author: Ivo Beerens
categories:
- ESXi
- vadp
- vpshere
date: "2011-05-02T16:15:53Z"
guid: http://www.ivobeerens.nl/?p=840
id: 840
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- esxi
- vadp
- vSphere
title: Unable to commit snapshot after VADP backup
url: /2011/05/02/unable-to-commit-snapshot-after-vadp-backup/
---

<font color="#000000"></font>

<font color="#000000">When doing a health check I found the following error during the remove if a snapshot in vCenter:</font>

> **<font color="#000000">Unable to access file <unspecified filename> since it is locked</font>**

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/05/image_thumb.png "image")</font>](http://localhost/wp-content/uploads/2011/05/image.png)

<font color="#000000">There is a problem when committing the snapshot after the vStorage APIs for Data Protection (VADP) backup of the VM.</font>

<font color="#000000">In the snapshot manager in vCenter there was no snapshot visible. I needed the be sure that no snapshot is active in the background. This can be very dangerous when snapshots still active and grows. The snapshot can allocate al the free disk space on the datastore and slow down the VM.</font>

<font color="#000000">By enabling remote Tech Support Mode (TSM) on the VMware ESXi server I needed the be sure that no snapshot is active by using the following command:</font>

> <font color="#000000">**find /vmfs/volumes/ -iname "\*delta.vmdk"**</font>

[<font color="#000000">![2011-05-02 15h16_20](http://localhost/wp-content/uploads/2011/05/2011-05-02-15h16_20_thumb.jpg "2011-05-02 15h16_20")</font>](http://localhost/wp-content/uploads/2011/05/2011-05-02-15h16_20.jpg)

<font color="#000000">The command displays all the “delta.vmdk” snapshot files on all the VMFS volumes. This command show that the snapshot is still active. </font>

<font color="#000000">To “temporally” solve this problem:</font>

<font color="#000000">Create a manual snapshot of the VM. When the snapshot is created the old “Consolidate Helper-0” is added to the snapshot manager.</font>

[<font color="#000000">![2011-05-02 15h13_39](http://localhost/wp-content/uploads/2011/05/2011-05-02-15h13_39_thumb.jpg "2011-05-02 15h13_39")</font>](http://localhost/wp-content/uploads/2011/05/2011-05-02-15h13_39.jpg)

<font color="#000000">Hit the Delete All Button and the two snapshots are committed. When the remove snapshot task is completed (this can take a while depending on the size of the snapshot). Run the find command again and verify if the snapshot is committed.</font>

<font color="#000000">I see this problem lately with more customers who using VMware vSphere 4.1 Update 1 with different backup solutions such ad Symantec CommVault and Veeam that use VADP. Let’s create a support incident. </font>

<font color="#000000"></font>

<font color="#000000"> </font>

<font color="#000000"></font>
