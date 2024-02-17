---
author: Ivo Beerens
categories:
- vds
- vSphere
- vSphere Distributed Switch
- vsphere51
date: "2012-10-29T10:08:30Z"
guid: http://www.ivobeerens.nl/?p=1929
id: 1929
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- vds
- vSphere
- vSphere Distributed Switch
- vsphere51
title: Migrate to a new vCenter server with the vSphere Distributed Switch (VDS) enabled
  in vSphere 5.1
url: /2012/10/29/migrate-to-a-new-vcenter-server-with-the-vsphere-distributed-switch-vds-enabled-in-vsphere-5-1/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

Migrating to a new fresh vCenter server using the vSphere Distributed Switch (VDS) prior vSphere 5.1 is not a easy task. The VDS is part of the vCenter configuration. If you try to import hosts that have a VDS configuration to a new vCenter server the following warning will appear:

> The distributed Virtual Switch corresponding to the proxy switches d5 6e 22 50 dd f2 94 7b-a6 1f b2 c2 e6 aa 0f bf on the host does not exist in vCenter or does not contain the host.

Kenneth van Ditmarsch describes in his blog post “ [Migrate to new vCenter Server while using dvSwitches](http://virtualkenneth.com/2012/10/19/migrate-to-new-vcenter-server-while-using-dvswitches/)” how to migrate from a vCenter 4 server with a VDS switch to a new vCenter 5 server. This can be a risky and time consuming task task.

vSphere 5.1 supports to backup and restore the VDS configuration. This makes it possible to migrate the VDS configuration on a new vCenter server very easily, without to migrate the VDS first to the vSS on the old vCenter server and on the new vCenter server migrate the vSS to the VDS.

Here are the steps:

- Upgrade the old vCenter server to version 5.1
- Install a new vCenter 5.1 server and create a datacenter and cluster
- Export the DVS configuration on the old vCenter server
- Disable HA on the old cluster(s)
- Disconnect all the hosts on the old vCenter server
- Import all the hosts on the new vCenter server. The following warning is displayed and it is safe to ignore the warning:

[![image](http://localhost/wp-content/uploads/2012/10/image_thumb1.png "image")](http://localhost/wp-content/uploads/2012/10/image1.png)

- Import the VDS configuration on the new vCenter server

| [![image](http://localhost/wp-content/uploads/2012/10/image_thumb2.png "image")](http://localhost/wp-content/uploads/2012/10/image2.png) | [![image](http://localhost/wp-content/uploads/2012/10/image_thumb3.png "image")](http://localhost/wp-content/uploads/2012/10/image3.png) |
|---|---|

- Remove the disconnected hosts on the old vCenter server

After the VDS import, the warning will disappear and the VDS configuration is migrated to the new vCenter server.

**More information**

[VMware vSphere 5.1 – Network Config Backup and Restore video](http://youtu.be/cfjeHzvsrr0)
