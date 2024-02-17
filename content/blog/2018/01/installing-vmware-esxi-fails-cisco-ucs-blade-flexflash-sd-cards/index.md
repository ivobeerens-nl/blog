---
title: "Installing VMware ESXi fails on Cisco UCS Blades with FlexFlash SD cards"
date: "2018-01-31T20:42:22.000Z"
categories: 
  - "esxi"
tags: 
  - "cisco-ucs"
  - "esxi-2"
author: Ivo Beerens
---

> Operation failed
> 
> This program has encountered an error:
> 
> partedUtil failed with message: "Error: Can’t have a a partition outside the disk! Unable to read partition table for device /vmfs/devices/disks...................

[![](images/error-270x300.jpg)](images/error.jpg)

The solutions is simple, perform a format of the SD card in UCSM before installing VMware ESXi. The format option can be found under:

- Equipment -> Servers -> Select the server -> Inventory -> Storage - Controller -> Select the FlexFlash controller -> Format SD Cards

[![](images/flexflash-300x200.jpg)](images/flexflash.jpg)



