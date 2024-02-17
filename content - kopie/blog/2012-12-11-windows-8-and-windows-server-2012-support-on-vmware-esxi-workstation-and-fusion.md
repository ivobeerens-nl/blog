---
author: Ivo Beerens
categories:
- ESXi
- windows 8
- windows server 2012
date: "2012-12-11T13:39:03Z"
guid: http://www.ivobeerens.nl/?p=2084
id: 2084
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- esxi
- windows 8
- windows server 2012
title: Windows 8 and Windows Server 2012 support on VMware ESXi, Workstation and Fusion
url: /2012/12/11/windows-8-and-windows-server-2012-support-on-vmware-esxi-workstation-and-fusion/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

The following VMware releases are supported with Windows 8 and Windows Server 2012:

| **OS** | **Supported versions** |
|---|---|
| Windows 8 32/64 Bits | Workstation 9    Fusion 5.0    ESXi 5.0 U1    ESXi 5.1 |
| Windows Server 2012 64 Bits | Workstation 9    Fusion 5.0    ESXi 5.0 U1    ESXi 5.1 |

Windows 8 and Windows Server 2012 are supported on ESX 5.0 U1 and 5.1. Here are some things to watch when implementing Windows 8 or Windows Server 2012 on ESXi environment.

### vNIC

For Windows 8 and Windows Server 2012 the E1000e adapter is the default vNIC. The E1000e feature emulates a newer model of Intel Gigabit NIC (number 82574) in the virtual hardware. This is known as the "e1000e" vNIC. e1000e is available only on hardware version 8 (and newer) virtual machines in vSphere 5!

[![image](http://localhost/wp-content/uploads/2012/12/image_thumb7.png "image")](http://localhost/wp-content/uploads/2012/12/image7.png)

VMXNET 3

The VMXNET 3 is optimized for performance in a virtual machine. Because operating system vendors do not provide built-in drivers for this card, you must install VMware Tools to have a driver for the VMXNET3 network adapter available. The VMXNET3 is available only on hardware version 7 and newer!

### SCSI Disk controller

The default SCSI disk controller is the LSI Logic SAS.

PVSCSI

The Paravirtual SCSI (PVSCSI) adapters are high-performance storage adapters that can result in greater throughput and lower CPU utilization. When browsing through the FLP images there is no Windows Server 2012 driver available for the PVSCSI adapter.

[![image](http://localhost/wp-content/uploads/2012/12/image_thumb8.png "image")](http://localhost/wp-content/uploads/2012/12/image8.png)

The KB says nothing on Windows 8 or Server 2012 support ([Link](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1010398)). In the computability OS guide it stated the the PVSCSI adapter is supported on Windows Server 2012 and Windows 8.

[![image](http://localhost/wp-content/uploads/2012/12/image_thumb9.png "image")](http://localhost/wp-content/uploads/2012/12/image9.png)

Using the 2008 PVSCSI FLP image will install the PVSCSI driver in Windows 8 and Server 2012.

### Guest OS Customization support

Guest OS Customization support is only supported on Windows 8 and not on Windows Server 2012!

[![image](http://localhost/wp-content/uploads/2012/12/image_thumb10.png "image")](http://localhost/wp-content/uploads/2012/12/image10.png)

Link
