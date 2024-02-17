---
author: Ivo Beerens
categories:
- Home Lab
date: "2020-02-07T10:39:40Z"
guid: https://www.ivobeerens.nl/?p=7329
id: 7329
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- homelab
title: VMware homelab build of materials and configuration
url: /2020/02/07/vmware-homelab-build-of-materials-and-configuration/
---

William Lam has started a great initiative. William asked ([link](https://t.co/coVQqnxG9N)) everyone who owns a homelab to share there build of materials (BOM) and configuration so the vCommunity can benefit and learn from. I have a simple homelab configuration, the materials I used and configuration are listed below:

[![](http://localhost/wp-content/uploads/2020/02/Tekening1-300x195.jpg)](http://localhost/wp-content/uploads/2020/02/Tekening1.jpg)

**Internet**

Cable modem in bridge mode with 250 Mbit/s down and 25 Mbit/s upload.

**Router**

Ubiquiti EdgeRouter Lite 3-Port router

**Access Point**

Ubiquiti UniFi AP AC PRO

**Layer 2 switches**

2 x HP ProCurve 1810G (8 x 1GbE) manageable switches.

**Compute**

Shuttle SH370R6 Plus and a Shuttle SH370R8 Plus. Each barebone has:

- 500 W Plus Silver PSU
- Intel Core i7 8700 with 6 cores and 12 threads
- 64 GB memory
- Samsung 970 EVO 1 TB m.2
- Kingston datatraveler 100 G3 32 GB USB disk
- 2 x 1 GbE Network cards

[![](http://localhost/wp-content/uploads/2020/02/homelab-300x290.jpg)](http://localhost/wp-content/uploads/2020/02/homelab-scaled.jpg)

**Network Attached Storage** (NAS)

QNAP TS-251+ NAS with two Western Digital (WD) Red 8 TB disk in a RAID-1 configuration.

**Software**

- VMware vSphere (ESXi, vCenter)
- VMware vSAN
- VMware Horizon
- VMware NSX-V and NSX-T
- vRealize products
- IoT stuff

**Build of materials (BOM)**

| **Components** | **Costs ~** | **Links to blog posts** |
|---|---|---|
| Ubiquiti EdgeRouter Lite 3-Poort Router | € 93 |  |
| Ubiquiti UniFi AP AC PRO | € 136 |  |
| HP ProCurve 1810G | € 75 each. Not available anymore. |  |
| Shuttle SH370R6 Plus | € 1200 | [Link](http://localhost/2019/01/30/home-lab-extension-with-a-shuttle-sh370r6-plus/) |
| Shuttle SH370R8 | € 1200 | [Link](http://localhost/2019/06/04/using-the-shuttle-sh370r8-as-home-lab-server-with-vmware-esxi/) |
| QNAP TS-251+ | € 314 |  |
| 2 x Western Digital (WD) Red 8 TB | € 258 each. Total € 516 |  |

An overview of all the submitted community homelabs can be found here, [link.](https://github.com/lamw/homelab)
