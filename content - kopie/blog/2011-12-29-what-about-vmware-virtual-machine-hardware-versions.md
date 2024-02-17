---
author: Ivo Beerens
categories:
- hardware
- Tools
- VMware
- vpshere
date: "2011-12-29T15:44:42Z"
guid: http://www.ivobeerens.nl/?p=1199
id: 1199
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hardware
- Tools
- version
- VMware
title: What about VMware Virtual Machine hardware versions
url: /2011/12/29/what-about-vmware-virtual-machine-hardware-versions/
---

<font color="#000000"></font>

<font color="#000000">I often get the question: “What Virtual Machine hardware version do I need?”. </font>

<font color="#000000">It depends on the features you need. If you want for example use the “Changed Blocked Tracking (CBT)” feature, you need at least hardware version 7.</font>

<font color="#000000">In ESX 3.x hardware version 4 is introduced, in vSphere 4.x hardware version 7 is introduced and in vSphere 5 hardware version 8 is introduced. Here is an overview of the hardware version and the features they have:</font>

<font color="#000000"></font>

| **<font color="#000000">Hardware version </font>** | **<font color="#000000">Features</font>** | **<font color="#000000">Products</font>** |
|---|---|---|
| <font color="#000000" size="4">8</font> | <font color="#000000">**– Up to 32 vCPUs per VM    – Maximum 1 TB RAM per VM    – 3-D graphics and high-definition audio    – Smart-card reader support    – USB 3.0 devices are supported    – Improved network driver for the E1000e** network adapter, provided by VMware tools    – Greater resources are available with vCloud Director 1.5</font> | <font color="#000000">Hardware version 8 is the default for new VM in:    – **ESX 5.x**    – Fusion 4.x    – Workstation 8.x    – Player 4.x</font> |
| <font color="#000000" size="4">7</font> | <font color="#000000">– **Serial Attached SCSI (SAS) virtual device for Microsoft Cluster Service** — Provides support for running Windows Server 2008 in a Microsoft Cluster Service configuration.    – **IDE virtual device** — Ideal for supporting older operating systems that lack SCSI drivers.    – **VMXNET Generation 3.** VMXNET is optimized for performance in a virtual machine    – **Virtual Machine Hot Plug Support**— Provides support for adding and removing virtual devices, adding virtual CPUs, and adding memory to a virtual machine without having to power off the virtual machine.    – **Change Block Tracking (CBT) support.** Incease VADP backups</font> | <font color="#000000">Hardware version 7 is the default for new VM in:    – **ESX 4.x**    – Fusion 3.x    – Fusion 2.x    – Workstation 7.x &amp; 6.5    – Player 3.x    – Server 2.x</font> |
| <font color="#000000" size="4">4</font> | <font color="#000000"></font> | <font color="#000000">Hardware version 4 is the default for new VM in:    – **ESX 3.x**    – ACE 2.x    – Fusion 1.x    – Player 2.x</font> |
| <font color="#000000" size="4">3</font> |  | <font color="#000000">Hardware version 3 is the default for new VM in:    – ESX 2.x    – GSX Server 3.x</font> |

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

**<font color="#000000"></font>**

<font color="#000000">**Considerations before upgrading the hardware version of the VM:**</font>

<font color="#000000">– Important to know is that upgrading the hardware version of the VM requires downtime!</font>

<font color="#000000">– Virtual machines with hardware version 7 can only run on ESX(i) 4.x and ESXi 5.x. Virtual machines with hardware version 8 can **only** run on ESXi 5.x</font>

<font color="#000000">– When you upgrade from virtual hardware version 4 to version 8, the upgrade is reversible if you take a virtual machine backup or snapshot before performing the upgrade.</font>

<font color="#000000">– To automate this process, consider using Update Manager for virtual machine upgrades</font>

<font color="#000000">– Update Manager takes automatic snapshots before performing virtual machine upgrades</font>

<font color="#000000">– Be sure to upgrade first the VMware tools of the VM. I you upgrade the virtual hardware before you upgrade VMware Tools, the virtual machine might lose its network settings </font>

<font color="#000000">– Verify that all VMs and .VMDK files are stored on VMFS3, VMFS5 or NFS volumes</font>

<font color="#000000"></font>

<font color="#000000"> </font>

<font color="#000000">**Steps in the hardware version upgrade process:**</font>

<font color="#000000">– Do an inventory on the current hardware and VMware tools versions. This can be done for example by using the vCenter client, RVtools utility or PowerCLI </font>

<font color="#000000">– Install or upgrade the VMware tools (reboot required)</font>

<font color="#000000">– Power on the VM</font>

<font color="#000000">– Before upgrading create a backup or snapshot of the VM</font>

<font color="#000000">– Backup the NIC IP settings with the VMUpgradeHelper.exe command. More information can be found </font><font color="#000000">here</font>

<font color="#000000">– Power off the VM</font>

<font color="#000000">– Upgrade Virtual Hardware</font>

<font color="#000000">– Start VM (reboot after the new hardware is discovered)</font>

<font color="#000000">– Check if all the IP addresses are correct</font>

<font color="#000000"></font>

<font color="#000000"> </font>

<font color="#000000">**Downgrade methods:**</font>

<font color="#000000">There is no button in vCenter to revert back to an earlier Hardware version. Here are two methods to go back to an earlier version of the hardware version:</font>

<font color="#000000">– Create before upgrading the hardware version a snapshot when the VM is powered down.</font>

<font color="#000000">– Using VMware Converter </font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"> </font>

<font color="#000000">**Upgrading issues to know about:**</font>

<font color="#000000">– Upgrading virtual hardware in ESX 4.x may cause Windows 2008 disks to go offline (more information can be found </font>[<font color="#000000">here</font>](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1013109)<font color="#000000">)</font>

<font color="#000000">– After a hardware version upgrade the configuration can be messed up on for example Microsoft ISA, Microsoft NLB clusters and RSA servers </font>

<font color="#000000">– After upgrading a Windows virtual machine from hardware version 4 to hardware version 7, virtual NIC settings (such as static IP configuration) are lost. Make sure you backup the VM IP settings with the VMUpgradeHelper.exe command. More information can be found </font><font color="#000000">here</font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"> </font>

<font color="#000000"></font>

\[ad#banner\]
