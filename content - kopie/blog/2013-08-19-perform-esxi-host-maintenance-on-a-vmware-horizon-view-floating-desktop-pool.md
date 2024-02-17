---
author: Ivo Beerens
categories:
- horizon
- maintenance
- view
- VMware
date: "2013-08-19T15:02:47Z"
guid: http://www.ivobeerens.nl/?p=2416
id: 2416
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- maintenance
- vmware horizon view
title: Perform ESXi host maintenance on a VMware Horizon View floating desktop pool
url: /2013/08/19/perform-esxi-host-maintenance-on-a-vmware-horizon-view-floating-desktop-pool/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

When you need to perform maintenance (planned downtime) on an ESXi host which is part of a floating pool the following steps can be be taken:

These steps are only required when using local storage for the linked clones!

1. In the VMware Horizon View Administrator, edit the pool and uncheck the datastore for the host on which maintenance is required. By unchecking the datastore no new desktops are provisioned to this host
2. In the pool settings modify the “Delete or refresh desktop on logoff” to “Delete Immediately”
3. **Optionally**: In the pool settings modify the “Automatically or logoff after disconnect” to 240 minutes or less so that disconnected sessions are removed.
4. Decrease the maximum number of desktops in the Provisioning settings so it matches the cluster
5. When there are no more floating desktops on the ESXi host place, it in maintenance mode
6. Perform maintenance of the ESXi host.

**![](https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcRCbKVj0PVDXm9YtOoH1ulL0tyhAowAfum64F55WOmKzm5gCrHg)**

A good practice is to perform steps 1 till 4 a day before the actually maintenance of the ESXi host, so all the VDI desktops are removed. After the maintenance is done perform steps 1 to 6 by using the originally settings.
