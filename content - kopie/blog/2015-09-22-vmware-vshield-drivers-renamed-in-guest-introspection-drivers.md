---
author: Ivo Beerens
categories:
- Uncategorized
date: "2015-09-22T21:27:09Z"
guid: http://www.ivobeerens.nl/?p=4036
id: 4036
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:2;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
title: VMware vShield drivers renamed in Guest Introspection drivers
url: /2015/09/22/vmware-vshield-drivers-renamed-in-guest-introspection-drivers/
---

The vShield Endpoint drivers are renamed as Guest Introspection Drivers. In VMware Tools there are two drivers available:

- NSX File Introspection Driver (**vsepflt.sys**)
- NSX Network Introspection Driver (**vnetflt.sys**)

These drivers can be installed separately now and allows you to install the file driver without installing the network driver. To install the vShield Endpoint Thin Agent driver (vsepflt.sys), select the NSX File Introspection Driver in VMware tools under VMCI Driver.

[![vShield driver](http://localhost/wp-content/uploads/2015/09/vShield-driver-300x235.png)](http://localhost/wp-content/uploads/2015/09/vShield-driver.png)

For existing installations check if the vShield Endpoint Thin Agent driver is installed by using the following steps:

- Open ‘msinfo32’
- Select Software Environment (1)
- Select System Drivers (2)
- Search for the vsepflt driver (3) and check if the driver is running

[![vsepflt](http://localhost/wp-content/uploads/2015/09/vsepflt-300x132.png)](http://localhost/wp-content/uploads/2015/09/vsepflt.png)
