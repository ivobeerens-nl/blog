---
author: Ivo Beerens
categories:
- ESX
- ESXi
- vmfs
- VMware
date: "2011-12-19T15:05:20Z"
guid: http://www.ivobeerens.nl/2011/12/19/unable-to-create-vmfs-partition/
id: 1196
ssb_fbshare_counts:
- "4"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:4;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "4"
tags:
- ESX
- esxi
- VMware
title: Unable to create VMFS partition
url: /2011/12/19/unable-to-create-vmfs-partition/
---

<font color="#000000"></font>

<font color="#000000">On my home lab I tried to create a new VMFS volume on a RAID-0 disk set that was coming from another host. When creating the new VMFS volume from the vSphere client, the following error appeared:</font>

<font color="#000000" face="Courier New">Call “HostDatastoreSystem.QueryVmfsDatastoreCreateOptions” for object “datastoresystem-9” on vCenter Server “VC01″ failed.</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/12/image_thumb2.png "image")</font>](http://localhost/wp-content/uploads/2011/12/image2.png)

<font color="#000000"></font>

<font color="#000000">On the VMware ESXi 5 server I enabled “Local Tech Support Mode” (more information can be found </font>[<font color="#000000">here</font>](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1017910)<font color="#000000">), so I was able to logging in directly on the console and used the **fdisk-l** command to see the partition information on the disk. I notice that the disk contains four old partitions from another system.</font>

[<font color="#000000">![2011-12-16 18h37_25](http://localhost/wp-content/uploads/2011/12/2011-12-16-18h37_25_thumb.jpg "2011-12-16 18h37_25")</font>](http://localhost/wp-content/uploads/2011/12/2011-12-16-18h37_25.jpg)

<font color="#000000">I deleted the four partitions by using the following commands (**displayed in bold**):</font>

<font color="#000000">– **fdisk /dev/disk/mpx.vmhba3:C0:T1:LO** (see the above picture)</font>

<font color="#000000">– **p** (for printing the partition information and verify that you choose the right disk)</font>

<font color="#000000">– **d** and enter the partition numbers (**1**, **2**, **3**, and **4)** for deleting the partition</font>

<font color="#000000">**– p** to verify that all the partitions are deleted</font>

<font color="#000000">– **w** to write the modifications to disk</font>

<font color="#000000"> </font>

<font color="#000000">After the deletion of the old partitions I was able to create the VMFS volume on the RAID-0 disk set.</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/12/image_thumb3.png "image")</font>](http://localhost/wp-content/uploads/2011/12/image3.png)

<font color="#000000"></font>

<font color="#000000"></font>
