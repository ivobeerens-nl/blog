---
author: Ivo Beerens
categories:
- Uncategorized
date: "2020-09-17T16:51:32Z"
guid: https://www.ivobeerens.nl/?p=7598
id: 7598
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hyper-v
- VMware
- workstation
title: Run VMware Workstation and Microsoft Hyper-V together in Windows 10
url: /2020/09/17/run-vmware-workstation-and-microsoft-hyper-v-together-on-windows-10/
---

In 2013 I wrote a blog post that it was not possible to run VMware Workstation when the Hyper-V role was enabled ([link](http://localhost/2013/12/16/running-hyper-v-and-vmware-workstation-on-windows-8-x/)). Since VMware Workstation 15.5 it is possible to run VMware Workstation and the Hyper-V role together.

Requirements:

- Windows 10 2004 or newer
- VMware Workstation 15.5.5 or newer
- Supported CPU: Intel Sandy Bridge or an AMD Bulldozer or newer

I tested this with my Windows 10 laptop with the Hyper-V role enabled, the Windows Subsystem for Linux running, and VMware Workstation 16 Pro. In Hyper-V and VMware Workstation a Windows 10 VM is running. In the screenshot below you see all the components started:

[![](http://localhost/wp-content/uploads/2020/09/1-300x164.jpg)](http://localhost/wp-content/uploads/2020/09/1-scaled.jpg)

This is very cool, now you can run VMware Workstation and Hyper-V role at the same time even with the WSL active.
