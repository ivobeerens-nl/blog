---
author: Ivo Beerens
categories:
- Hyper-V
- windows 8
- workstation
date: "2012-03-13T22:15:01Z"
guid: http://www.ivobeerens.nl/?p=1429
id: 1429
ssb_fbshare_counts:
- "15"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:15;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "15"
tags:
- hyper-v
- windows 8
- workstation
title: Enable Windows Server 8 Hyper-V in VMware Workstation
url: /2012/03/13/enable-windows-server-8-hyper-v-in-vmware-workstation/
---

<font color="#000000">VMware Workstation Technology Preview 2012 is available as download. The Technology Preview makes it possible for example to install and operate Windows 8 and Windows Server 8 in a VM and the possibility to nest VMs.</font>

<font color="#000000">I tested the installation of Windows Server 8 in VMware Workstation TP, enabled the Hyper-V role and run a Windows 7 64-bit VM in Hyper-V. Here are some screenshots (Hyper-V manager and the Windows 7 64 bit running in Hyper-V):</font>

[![image](http://localhost/wp-content/uploads/2012/03/image_thumb20.png "image")](http://localhost/wp-content/uploads/2012/03/image20.png)

[![image](http://localhost/wp-content/uploads/2012/03/image_thumb21.png "image")](http://localhost/wp-content/uploads/2012/03/image21.png)

<font color="#000000">To make the above configuration work, add to following options to the end of the VMX file before starting the Windows Server 8 installation:</font>

```
<pre lang="plain">
hypervisor.cpuid.v0 = FALSE
mce.enable = "TRUE"
```

<font color="#000000">The VMware Workstation TP VMs are started in debug mode which impacts the performance! </font>

[![image](http://localhost/wp-content/uploads/2012/03/image_thumb22.png "image")](http://localhost/wp-content/uploads/2012/03/image22.png)

<font color="#000000">More information can be found here:</font>

<font color="#000000">– </font>[<font color="#000000">VMware Workstation Technology Preview 2012 Overview</font>](http://communities.vmware.com/docs/DOC-18665)

<font color="#000000">– </font>[<font color="#000000">Download</font>](http://communities.vmware.com/community/vmtn/beta/workstationtp2012)

\[ad#banner\]
