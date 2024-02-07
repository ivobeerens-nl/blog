---
author: Ivo Beerens
categories:
- ESXi
date: "2018-09-16T09:19:57Z"
guid: https://www.ivobeerens.nl/?p=6482
id: 6482
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- bootable
- esxi
- usb
title: 'Quick tip: Create a bootable VMware ESXi stick'
url: /2018/09/16/quick-tip-create-a-bootable-vmware-esxi-key/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

There are multiple tools available to create a bootable VMware ESXi USB stick/drive/key such as:

- UNetbootin, [link](https://unetbootin.github.io/)
- Rufus, [link](https://rufus.ie/)

My favorite tool to create a VMware ESXi USB stick/key is Rufus. I use Rufus because it’s small, fast, Windows-based, open-sourced and the tool is updated frequently.

### Requirements

Requirements for creating a VMware ESXi key:

- Windows Operating System (Windows 7 or later)
- Rufus download
- VMware ESXi ISO download.

### Create a USB Stick

To create a VMware ESXi stick is easy. Perform the following steps:

- Start Rufus
- Select the USB device
- Select the ESXi ISO
- Press Start
- Data on the USB key will be destroyed.

[![](http://localhost/wp-content/uploads/2018/11/boot-205x300.png)](http://localhost/wp-content/uploads/2018/11/boot.png) [![](http://localhost/wp-content/uploads/2018/11/2-205x300.png)](http://localhost/wp-content/uploads/2018/11/2.png)

When the progress status bar is READY, the VMware ESXi bootable is created and ready to boot. I tested the creation of the ESXi USB stick with the latest version of VMware ESXi 6.7 and VMware ESXi 7.
