---
author: Ivo Beerens
categories:
- vcenter
- vcsa
date: "2015-02-02T22:11:55Z"
guid: http://www.ivobeerens.nl/?p=3350
id: 3350
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- vCenter
- vcsa
- VMware
title: What&#8217;s new in the vCenter Server Appliance (vCSA) 6.0
url: /2015/02/02/whats-new-vsphere-6-vcenter-server-appliance-vcsa/
---

What’s new in the vCenter Server Appliance (vCSA) 6.0:

- ISO with an easy guided Installer
- Different deployment options possible during the guided installer such as: 
    - Install vCenter Server
    - Install Platform Services Controller
    - Install vCenter Server with an Embedded Platform Controller (default)
- Scripted install. Values can be specified in a template file
- Embedded vPostgres database. As external database Oracle is supported.
- IPv6 Support
- Enhanced Linked mode support
- VMware Data Protection (VDP) support for backup and recovery
- Based on a hardened Suse Linux Enterprise 11 SP3 (64-bit)
- The minimum (Up to 20 hosts and 400 VMs) appliance requirements for the VCSA are: 
    - 2 vCPU
    - 8 GB memory
    - ~ 100 GB diskspace
- Is has the same feature parity as vCenter Windows:

[![scalability](http://localhost/wp-content/uploads/2015/02/scalability-300x128.png)](http://localhost/wp-content/uploads/2015/02/scalability.png)

What are we missing:

- Still no Microsoft SQL database support.
- Possibility to separate roles of the vCenter
- VMware Update Manager is not included in the appliance. Still need an additional Windows Server for VMware Update Manager (VUM)
- Clustering of the vCenter Server Appliance

[![2015-02-02_11h45_45](http://localhost/wp-content/uploads/2015/02/2015-02-02_11h45_45-300x142.png)](http://localhost/wp-content/uploads/2015/02/2015-02-02_11h45_45.png) [![2015-02-02_11h46_18](http://localhost/wp-content/uploads/2015/02/2015-02-02_11h46_18-300x192.png)](http://localhost/wp-content/uploads/2015/02/2015-02-02_11h46_18.png) [![database](http://localhost/wp-content/uploads/2015/02/database-300x193.png)](http://localhost/wp-content/uploads/2015/02/database.png) [![IP](http://localhost/wp-content/uploads/2015/02/IP-300x193.png)](http://localhost/wp-content/uploads/2015/02/IP.png) [![psc](http://localhost/wp-content/uploads/2015/02/psc-300x193.png)](http://localhost/wp-content/uploads/2015/02/psc.png) [![single](http://localhost/wp-content/uploads/2015/02/single-300x193.png)](http://localhost/wp-content/uploads/2015/02/single.png) [![size](http://localhost/wp-content/uploads/2015/02/size-300x192.png)](http://localhost/wp-content/uploads/2015/02/size.png) [![vcsa console](http://localhost/wp-content/uploads/2015/02/vcsa-console-300x228.png)](http://localhost/wp-content/uploads/2015/02/vcsa-console.png)
