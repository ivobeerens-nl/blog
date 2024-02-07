---
author: Ivo Beerens
categories:
- vpshere
- vpshere 5
- vSphere
- vsphere5
date: "2013-12-03T10:49:04Z"
guid: http://www.ivobeerens.nl/?p=2560
id: 2560
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- esxi
- fusion-io
- ssd
- upgrade
- VMware
- vSphere
title: After upgrading vSphere 4 to 5 the Fusion-IO card is in minimal mode
url: /2013/12/03/upgrading-vsphere-5-x-fusion-io-card-disappeared/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

Last week I did a VMware vSphere and VMware View 4 to 5 upgrade. The ESXi servers for the VMware View environment uses Fusion-IO (HP IO Accelerators) PCI flash cards for there non-persistent VDI pools. After the upgrade to vSphere 5.1 I imported the latest Fusion-IO drivers and created a baseline in vSphere Update Manager (VUM) and deployed the new drivers to the cluster.

| [![image](http://localhost/wp-content/uploads/2013/10/image_thumb10.png "image")](http://localhost/wp-content/uploads/2013/10/image10.png) | [![image](http://localhost/wp-content/uploads/2013/10/image_thumb11.png "image")](http://localhost/wp-content/uploads/2013/10/image11.png) |
|---|---|

After the installation of the Fusion-IO drivers on the ESXi hosts, the Fusion-IO card was not listed in the vSphere (Web) client. Via SSH I make a connection the the ESXi servers. When i run the **fio-status** command the following warning appeared:

> Driver is in Minimal mode: The firmware on this device is not compatible with the currently installed version of the driver.
> 
> ACTIVE WARNINGS: The ioMemory is currently running in a minimal state.

[![image](http://localhost/wp-content/uploads/2013/10/image_thumb12.png "image")](http://localhost/wp-content/uploads/2013/10/image12.png)

The warning means that the firmware needs to be upgraded. I uploaded the firmware to a central datastore and run the following command:

fio-update-iodrive *firmwarefilename*.fff

[![image](http://localhost/wp-content/uploads/2013/10/image_thumb13.png "image")](http://localhost/wp-content/uploads/2013/10/image13.png)

When the firmware upgrade completed, the ESXi servers needed to restart.

[![image](http://localhost/wp-content/uploads/2013/10/image_thumb14.png "image")](http://localhost/wp-content/uploads/2013/10/image14.png)

After the rebootI checked the status with the **fio-status** command again. The Fusion-IO card is out of minimal mode.

[![image](http://localhost/wp-content/uploads/2013/10/image_thumb15.png "image")](http://localhost/wp-content/uploads/2013/10/image15.png)

[![image](http://localhost/wp-content/uploads/2013/12/image1_thumb.png "image")](http://localhost/wp-content/uploads/2013/12/image11.png)

After the firmware upgrade the Fusion-IO card is listed again.
