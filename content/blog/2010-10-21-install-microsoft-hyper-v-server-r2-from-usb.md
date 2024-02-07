---
author: Ivo Beerens
categories:
- Hyper-V
- usb
- windows 8
date: "2010-10-21T14:11:45Z"
guid: http://www.ivobeerens.nl/?p=682
id: 682
ssb_fbshare_counts:
- "6"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:6;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "6"
tags:
- boot
- hyper-v
- hyper-v r2
- usb
- windows 8
title: Create a bootable USB to install Windows 8 Server or  Hyper-V Server 8
url: /2010/10/21/install-microsoft-hyper-v-server-r2-from-usb/
---

<font color="#000000"></font>

<font color="#000000">Not all servers nowadays have DVD player installed. Sometimes it is handy to boot from USB and install for example Windows Server 8. </font><font color="#000000">Here’s a example how to make the USB stick bootable for the following OS versions:</font>

<font color="#000000">– Windows Server 8 </font>

<font color="#000000">– Hyper-V Server 8</font>

<font color="#000000">– Server 2008 R2 </font>

<font color="#000000">– Hyper-V Server R2 </font>

### **<font color="#000000">Preparation:</font>**

<font color="#000000">– Need 4 GB USB memory stick or more</font>

<font color="#000000">– Download the desired ISO and save it</font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000">Stick the USB stick on a free USB port on your computer equipped with a Windows OS. For this example I used Windows7 as Operating System. Clear the USB stick and create a partition on it by using the following command’s:</font>

<font color="#000000">Open the command prompt ((make sure you run the cmd prompt as administrator)</font>

<font color="#000000">Commands:</font>

```
<pre lang="plain">diskpart 
list disk "list the disk in your system including the USB"
select disk "USB number"
clean
create partition primary
active
format fs=fat32 quick
assign
exit
```

<font color="#000000">Mount the ISO and copy all the content of the desired ISO to USB stick. For mounting the ISO I used “Deamon Tools Lite”.</font>

<font color="#000000">Now the bootable stick is ready for use. Boot your server with the stick and your able to install Windows 8, Windows 8 Server, 2008 R2 or Hyper-V server 8.</font>

<font color="#000000"></font>

\[ad#banner\]

<font color="#000000"></font>

```
```
