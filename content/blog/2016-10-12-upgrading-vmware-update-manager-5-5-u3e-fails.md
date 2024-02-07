---
author: Ivo Beerens
categories:
- VMware
date: "2016-10-12T14:24:22Z"
guid: http://www.ivobeerens.nl/?p=4795
id: 4795
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:2;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
title: Upgrading VMware Update Manager to 5.5 U3e fails
url: /2016/10/12/upgrading-vmware-update-manager-5-5-u3e-fails/
---

When upgrading VMware Update Manager (VUM) to 5.5 Update 3e the following error occurs:

> VMware Workstation unrecoverable error: (vthread-3) GetProcAddress: Failed to resolve ENGINE\_load\_aesni: 127

[![update-manager-error](http://localhost/wp-content/uploads/2016/10/Update-Manager-Error-300x159.png)](http://localhost/wp-content/uploads/2016/10/Update-Manager-Error.png)

This issue occurs when upgrading to VMware Update Manager to 5.5 Update 3e. I’ve seen this error when upgrading to 5.5U3e at different customer sites.

Here is a quick workaround:

- Uninstall VMware Update Manager and the VMware Update Manager plugins. The database is preserved, all the configuration data is stored in this database.
- Install VMware Update Manager and point to the existing VUM database
- Install the VUM plugin

Within a couple of minutes you’re running VMware Update Manager 5.5 U3e.

There is also a VMTN forum post about this issue, [link](https://communities.vmware.com/thread/541951?start=0&tstart=0)
