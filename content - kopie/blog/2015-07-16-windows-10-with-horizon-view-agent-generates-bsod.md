---
author: Ivo Beerens
categories:
- Horizon View
- Windows 10
date: "2015-07-16T15:18:19Z"
guid: http://www.ivobeerens.nl/?p=3910
id: 3910
ssb_fbshare_counts:
- "3"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:3;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "3"
tags:
- Horizon View
- windows 10
title: Windows 10 with Horizon View Agent generates BSOD
url: /2015/07/16/windows-10-with-horizon-view-agent-generates-bsod/
---

After installing the VMware Horizon View Agent (6.1.1) on a Windows 10 (tested with build 10240), it generates a Blue Screen Of Death (BSOD) when pressing Ctrl+Alt+Del/Ins.

[![PSOD](http://localhost/wp-content/uploads/2015/07/PSOD-300x233.png)](http://localhost/wp-content/uploads/2015/07/PSOD.png)

The error is: DRIVER\_IRQ\_NOT\_LESS\_OR\_EQUAL (kbdclass.sys).

To fix the problem (The solution was found on the Microsoft Community site, [link](http://answers.microsoft.com/en-us/insider/forum/insider_wintp-insider_devices/build-10130-enterprise-x64-bsod-with-vmware/d8c52293-2f4f-42fd-86dc-b002b3ae8b09)):

- RDP to the Windows 10 VM
- Edit HKLM\\SYSTEM\\CurrentControlSet\\Control\\Class\\{4D36E96B-E325-11CE-BFC1-08002BE10318}\\UpperFilters
- Put the kbdclass before the vmkbd value
- Reboot the VM

[![Upperclasses](http://localhost/wp-content/uploads/2015/07/Upperclasses-300x165.png)](http://localhost/wp-content/uploads/2015/07/Upperclasses.png) [![Uppper2](http://localhost/wp-content/uploads/2015/07/Uppper2-300x278.png)](http://localhost/wp-content/uploads/2015/07/Uppper2.png)

After changing the UpperFilters value I was able to login the Horizon View desktop without BSOD.
