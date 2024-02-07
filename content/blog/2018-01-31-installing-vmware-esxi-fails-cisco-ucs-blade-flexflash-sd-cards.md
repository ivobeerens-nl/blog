---
author: Ivo Beerens
categories:
- ESXi
date: "2018-01-31T21:42:22Z"
guid: https://www.ivobeerens.nl/?p=5422
id: 5422
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Cisco UCS
- esxi
title: Installing VMware ESXi fails on Cisco UCS Blades with FlexFlash SD cards
url: /2018/01/31/installing-vmware-esxi-fails-cisco-ucs-blade-flexflash-sd-cards/
---

When implementing a new Cisco UCS environment I encountered the following error when trying to install VMware ESXi 6.5 on a Cisco UCS Blade server with a FlexFlash SD card:

> Operation failed
> 
> This program has encountered an error:
> 
> partedUtil failed with message: “Error: Can’t have a a partition outside the disk!  
> Unable to read partition table for device /vmfs/devices/disks……………….

[![](http://localhost/wp-content/uploads/2018/01/error-270x300.jpg)](http://localhost/wp-content/uploads/2018/01/error.jpg)

The solutions is simple, perform a format of the SD card in UCSM before installing VMware ESXi. The format option can be found under:

- Equipment -> Servers -> Select the server -> Inventory -> Storage – Controller -> Select the FlexFlash controller -> Format SD Cards

[![](http://localhost/wp-content/uploads/2018/01/flexflash-300x200.jpg)](http://localhost/wp-content/uploads/2018/01/flexflash.jpg)
