---
author: Ivo Beerens
categories:
- haswell
- Home Lab
- Whitebox
date: "2013-06-25T18:12:29Z"
guid: http://www.ivobeerens.nl/?p=2361
id: 2361
ssb_fbshare_counts:
- "3"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:3;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "3"
tags:
- esxi
- haswell
- Home Lab
- hyper-v
- Whitebox
title: Haswell low power whitebox for ESXi and Hyper-V
url: /2013/06/25/haswell-low-power-whitebox-for-esxi-and-hyper-v/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

I was searching for a new whitebox for my home lab. I had the following requirements for the new whitebox:

- Low power consumption for 24×7 running
- >16 GB memory
- Expansion slots for PCI(-E) cards
- Good performance
- Low noise

A couple of weeks ago Intel released the new 4th generation Haswell CPUs that consumes less power. Seems to be interesting option for building a low power consumption whitebox. So I did some research and ordered the following hardware components:

| CPU | i5 4570S Boxed | [![foto-7_thumb1](http://localhost/wp-content/uploads/2013/06/foto-7_thumb1_thumb.jpg "foto-7_thumb1")](http://localhost/wp-content/uploads/2013/06/foto-7_thumb1.jpg) |
|---|---|---|
| Motherboard | Gigabyte GA-Z87-D3HP | ![](http://ic.tweakimg.net/ext/i/imagemedium/1370259171.png) |
| Memory | Corsair Vengeance 4 x 8 GB DDR3 PC3-12800 (DDR3-1600) 32GB | ![](http://ic.tweakimg.net/ext/i/imagemedium/1341612548.jpeg) |
| Power Supply | Seasonic G-360 80 Plus Gold | ![](http://ic.tweakimg.net/ext/i/1346765333.jpeg) |

The following components I reused:

- The case
- 2 Intel PCI-e NICS
- A SSD drive

**CPU**

Haswell is the codename for the 4th generation Intel Core processors. One of the big improvements of the Haswell CPUs is the idle power consumption. The Intel S-version is also a low-power CPU. It contains 4 cores and has a 65W TDP. The processor supports vPro, VT-x, VT-d, EPT etc. A CPU cooler is in the box included. For the full specifications look [here](http://ark.intel.com/products/75044/Intel-Core-i5-4570S-Processor-6M-Cache-up-to-3_60-GHz).

**Motherboard**

The Gigabyte GA-Z87-D3HP is a socket 1150 motherboard. The board has 4 memory sockets that support DDR3 memory up to 32 GB. It has onboard graphics , 6 x SATA 6 Gb/s connectors, a Intel WG-217v LAN adapter and the following expansion slots:

- 1 x PCI Express x16 slot
- 1 x PCI Express x16 slot, running at x4
- 2 x PCI Express x1 slots
- 2 x PCI slots

**Memory**

For the memory I choose the Corsair Vengeance CML32GX3M4A1600C10 4 x 8 PC3-12800 (DDR3-1600) CL10 kit. All the four memory sockets on the board are filled with a 8 GB module (total = 32 GB memory).

**Power Supply**

The Seasonic G-360 power supply has a 80 Plus Gold certification. This is a great power supply with high efficiency and low noise..

#### Hypervisor support

I tested VMware ESXi 5.1 Update 1 and vSphere 5.5 and Microsoft Windows Server 2012 with the Hyper-V role installed.

**VMware ESXi**

The onboard Intel I217-V NIC is not recognized by ESXi 5.1 Update 1. To get the I217-V NIC working in ESXi5.x read the blog post found [here](http://localhost/2013/09/20/enable-the-intel-i217-v-network-card-in-vmware-esxi/). I reused 2 Intel PCI-e NICs, one for LAN and the other for iSCSI and NFS traffic. The onboard SATA controller (Lynx Point AHCI) is recognized. I use an existing SSD for booting ESXi and running some important VMs. But is is possible to boot ESXi from USB stick. The other VMs are on NAS device. Passthrough is supported by the CPU and motherboard.

| [![image](http://localhost/wp-content/uploads/2013/06/image12_thumb.png "image")](http://localhost/wp-content/uploads/2013/06/image121.png) | [![image](http://localhost/wp-content/uploads/2013/06/image15_thumb.png "image")](http://localhost/wp-content/uploads/2013/06/image151.png) |
|---|---|
| [![image](http://localhost/wp-content/uploads/2013/06/image6_thumb.png "image")](http://localhost/wp-content/uploads/2013/06/image61.png) | [![image](http://localhost/wp-content/uploads/2013/06/image9_thumb.png "image")](http://localhost/wp-content/uploads/2013/06/image91.png) |

**Microsoft Windows Server 2012 with the Hyper-V role**

I tested Windows Server 2012 with the Hyper-V role enabled. The The onboard Intel I217-V NIC is not recognized by default. In the “[Enable the Intel I217-V NIC in Windows Server 2012](http://localhost/2013/06/24/enable-the-intel-i217-v-nic-in-windows-server-2012/)” blog post I explain how to enable the I217-V NIC Windows Server 2012.

| [![image](http://localhost/wp-content/uploads/2013/06/image18_thumb.png "image")](http://localhost/wp-content/uploads/2013/06/image181.png) | [![image](http://localhost/wp-content/uploads/2013/06/image22_thumb.png "image")](http://localhost/wp-content/uploads/2013/06/image221.png) |
|---|---|
| [![image](http://localhost/wp-content/uploads/2013/06/image27_thumb.png "image")](http://localhost/wp-content/uploads/2013/06/image271.png) | ![image](http://localhost/wp-content/uploads/2013/06/image_thumb29.png) |

**Power consumption**

The whitebox consumes a maximum between 40-50 W. When idle (and that is often) it consumes only 28 a 29 W!

[![foto (8)](http://localhost/wp-content/uploads/2013/06/foto-8_thumb.jpg "foto (8)")](http://localhost/wp-content/uploads/2013/06/foto-8.jpg)

The whitebox components cost about €615. and will be used for running VMs 24×7. The whitebox meets all the requirements I had.
