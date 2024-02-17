---
title: "What's new in the vCenter Server Appliance (vCSA) 6.0"
date: "2015-02-02T21:11:55.000Z"
categories: 
  - "vcenter-2"
  - "vcsa"
tags: 
  - "vcenter"
  - "vcsa"
  - "vmware"
---

What's new in the vCenter Server Appliance (vCSA) 6.0:

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

[![scalability](images/scalability-300x128.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/02/scalability.png)

What are we missing:

- Still no Microsoft SQL database support.
- Possibility to separate roles of the vCenter
- VMware Update Manager is not included in the appliance. Still need an additional Windows Server for VMware Update Manager (VUM)
- Clustering of the vCenter Server Appliance

 

[![2015-02-02_11h45_45](images/2015-02-02_11h45_45-300x142.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/02/2015-02-02_11h45_45.png) [![2015-02-02_11h46_18](images/2015-02-02_11h46_18-300x192.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/02/2015-02-02_11h46_18.png) [![database](images/database-300x193.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/02/database.png) [![IP](images/IP-300x193.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/02/IP.png) [![psc](images/psc-300x193.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/02/psc.png) [![single](images/single-300x193.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/02/single.png) [![size](images/size-300x192.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/02/size.png) [![vcsa console](images/vcsa-console-300x228.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/02/vcsa-console.png)
