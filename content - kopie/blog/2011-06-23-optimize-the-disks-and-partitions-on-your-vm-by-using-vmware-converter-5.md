---
author: Ivo Beerens
categories:
- converter
- VMware
date: "2011-06-23T13:24:21Z"
guid: http://www.ivobeerens.nl/?p=901
id: 901
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- converter
- VMware
title: Optimize the disk(s) and partition(s) on your VM by using VMware Converter
  5
url: /2011/06/23/optimize-the-disks-and-partitions-on-your-vm-by-using-vmware-converter-5/
---

<font color="#000000">By using VMware Converter 5 the following disk optimizations can be easily done on your existing VM:</font>

<font color="#000000">– Convert one or more partition(s) on single disk to partitions on a separate disks. When you want to increase disk space on the C: partition this is a problem because of the D partition is on the same disk.</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/06/image_thumb1.png "image")</font>](http://localhost/wp-content/uploads/2011/06/image1.png)

<font color="#000000">– Resize one or more partition(s)</font>

<font color="#000000">– Align on or more disks. (not needed anymore for Microsoft Windows 2008, Windows Vista or greater). This example shows a partition that is not aligned</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/06/image_thumb2.png "image")</font>](http://localhost/wp-content/uploads/2011/06/image2.png)

<font color="#000000">– Adjust the cluster size</font>

<font color="#000000"></font>

**<font color="#000000"></font>**

**<font color="#000000">V2V procedure:</font>**

<font color="#000000">– Power down the VM</font>

<font color="#000000">– In VMware Converter select “Convert Machine”</font>

<font color="#000000">– Follow the instructions on the screen till you got the options screen</font>

<font color="#000000">– Edit the “**Data to copy**”</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/06/image_thumb3.png "image")</font>](http://localhost/wp-content/uploads/2011/06/image3.png)

<font color="#000000">– Change the “Data copy type” from “**Copy all disks and maintain layout**” in </font>

<font color="#000000">“**Select volumes to copy**”. </font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/06/image_thumb4.png "image")</font>](http://localhost/wp-content/uploads/2011/06/image4.png)

<font color="#000000">– Select “Advanced” and choose the “Destination” layout</font>

<font color="#000000">– Change the disk size (in the example we change the C-partition to 30GB)</font>

<font color="#000000">– Use “**Add Disk”**, the **VirtualDisk2** is created. </font>

<font color="#000000">– Move the partition down (in the example the E: partition)</font>

<font color="#000000">– Be sure that the “Create optimized partition layout” option is selected for all the disks. VMware Converter optimize the disk partitions alignment”</font>

<font color="#000000">– The cluster size in this example at the default value</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/06/image_thumb5.png "image")</font>](http://localhost/wp-content/uploads/2011/06/image5.png)

<font color="#000000">– After the V2V the VM has 2 disks, the partition size is increased and both disk are aligned.</font>

<font color="#000000"></font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/06/image_thumb6.png "image")</font>](http://localhost/wp-content/uploads/2011/06/image6.png)

<font color="#000000">Check the disk alignment by using msinfo32.exe</font>

<font color="#000000"> </font>

<font color="#000000"></font>

<font color="#000000">VMware Converter 5.0 is available as public beta and can be found </font><font color="#000000">here</font><font color="#000000">.</font>

<font color="#000000"></font>
