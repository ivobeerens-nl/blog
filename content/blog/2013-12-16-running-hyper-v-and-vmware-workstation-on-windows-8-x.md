---
author: Ivo Beerens
categories:
- Hyper-V
- VMware
- workstation
date: "2013-12-16T20:40:29Z"
guid: http://www.ivobeerens.nl/?p=2601
id: 2601
ssb_fbshare_counts:
- "9"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:8;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "9"
tags:
- hyper-v
- VMware
- workstation
title: Running Hyper-V and VMware Workstation on Windows 8.x
url: /2013/12/16/running-hyper-v-and-vmware-workstation-on-windows-8-x/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

For testing I use Hyper-V and VMware Workstation 10 on my laptop. One restriction of VMware Workstation is that it does not support VHDX disk files (yet). VMware Workstation support VHD files, so the VHDX files must be converted to a VHD first. After the conversion VMware Workstation can select the VHD as Hard Disk. This can takes some time.

| [![image](http://localhost/wp-content/uploads/2013/12/image_thumb2.png "image")](http://localhost/wp-content/uploads/2013/12/image2.png) | [![image](http://localhost/wp-content/uploads/2013/12/image_thumb3.png "image")](http://localhost/wp-content/uploads/2013/12/image3.png) |
|---|---|
| 1. VHD disk | 2. Convert options in Hyper-V |

That’s why I use Hyper-V on my laptop sometimes. When trying to start VMware Workstation the following error appears:

> VMware Workstation and Hyper-V are not compatible. Remove the Hyper-V role from the system before running VMware Workstation.

[![image](http://localhost/wp-content/uploads/2013/12/image_thumb4.png "image")](http://localhost/wp-content/uploads/2013/12/image4.png)

This is because the Hyper-V role is installed and this conflicts with VMware Workstation. To disable Hyper-V from starting the following command can be used:

<span style="font-family: 'Courier New';">bcdedit /set hypervisorlaunchtype off</span>

A reboot of of the Windows OS is necessary.

To enable the Hyper-V role again use the following command:

<span style="font-family: 'Courier New';">bcdedit /set hypervisorlaunchtype auto</span>

A reboot of of the Windows OS is necessary.
