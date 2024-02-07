---
author: Ivo Beerens
categories:
- VDI
- view
- windows 8
date: "2013-04-12T09:07:55Z"
guid: http://www.ivobeerens.nl/?p=2261
id: 2261
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- VDI
- view
- windows 8
title: Optimize Windows 8 for Virtual Desktop Infrastructure (VDI) environments
url: /2013/04/12/optimize-windows-8-for-virtual-desktop-infrastructure-vdi-environments/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

Optimize and tuning a Windows 8 desktop in a VDI environment is important to reduce for example the CPU, IOPS and the memory footprint. During the Microsoft Management Summit (MMS) 2013 a breakout session about optimizing a Windows 8 desktop for Virtual Desktop Infrastructure (VDI) is held. The session has three main subjects:

- **Microsoft Guidance for Windows 8 Configuration VDI desktop**. What version of Windows 8 do I need, how many CPUs, memory, disk partitioning etc.
- **Detailed Review of Component Configuration**. What services do I need to enable or disable, do I need to disable SuperFetch? All the optimization settings are available in VBS script
- **Recommendations for performance testing**. This section is about the (third party) tools that can be used to do performance testing.

. The Windows 8 VDI sizing and optimizations can be used for example on the following VDI solutions:

- VMware Horizon View
- Citrix XenDesktop
- Microsoft VDI

A Windows 8 VDI optimization VBS script is available. This script does all the optimization work for you. Review all the settings before executing if the fits for your environment! There will be a PowerShell version available in the future. The Windows 8 optimization VBS script can be found [here](http://blogs.technet.com/b/jeff_stokes/archive/2013/04/09/hot-off-the-presses-get-it-now-the-windows-8-vdi-optimization-script-courtesy-of-pfe.aspx).

When you want to use Windows 8 for in your VDI environment this session helps you to size, tune and optimize your Windows 8 VDI desktop. The Optimizing Windows 8 for Virtual Desktop Infrastructure session can found [here](http://channel9.msdn.com/Events/MMS/2013/DV-B308).
