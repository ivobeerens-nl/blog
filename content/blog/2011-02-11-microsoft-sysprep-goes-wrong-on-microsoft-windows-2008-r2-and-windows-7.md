---
author: Ivo Beerens
categories:
- sysprep
- Windows 2008 R2
- Windows 7
date: "2011-02-11T10:05:14Z"
guid: http://www.ivobeerens.nl/?p=771
id: 771
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- sysprep
- windows2008
- windows7
title: Sysprep goes wrong on Microsoft Windows 2008 R2 and Windows 7
url: /2011/02/11/microsoft-sysprep-goes-wrong-on-microsoft-windows-2008-r2-and-windows-7/
---

<font color="#000000"></font>

<font color="#000000">This week I encountered a problem with Sysprepping a Microsoft Windows 2008 R2 VM after cloning. I cloned an existing VM and used a Customization Specification in vSphere vCenter for the Sysprep. When the Sysprepped Microsoft Windows 2008 R2 VM reboots, the following message appears:</font>

> <font color="#000000">Windows could not finish configuring the system. To attempt to resume configuration, restart the computer.</font>

<font color="#000000">Every time when restarting the VM, the message appears. After some troubleshooting such as disable services and active software before the Sysprep I found Microsoft Knowledgebase article “***A Windows 7 or a Windows Server 2008 R2 image deployment process stops when you try to deploy the image on another computer***” </font>[*<font color="#000000">KB981542</font>*](http://support.microsoft.com/kb/981542)<font color="#000000">. It stated that the Sysprep problem occurs if the original operating system contains a registry key that is larger than 8 kilobytes (KB). After installing the hotfix I was able the Sysprep the Microsoft Windows 2008 R2 VM. The Sysprep problem occurs on Windows7 and Microsoft Windows 2008 R2.</font>

<font color="#000000"></font>
