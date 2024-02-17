---
title: "Migrate to a new vCenter server with the vSphere Distributed Switch (VDS) enabled in vSphere 5.1"
date: "2012-10-29T09:08:30.000Z"
categories: 
  - "vds"
  - "vSphere"
  - "vSphere-distributed-switch"
  - "vSphere51"
tags: 
  - "vds"
  - "vSphere"
  - "vSphere-distributed-switch"
  - "vSphere51"
author: Ivo Beerens
---

> The distributed Virtual Switch corresponding to the proxy switches d5 6e 22 50 dd f2 94 7b-a6 1f b2 c2 e6 aa 0f bf on the host does not exist in vCenter or does not contain the host.

Kenneth van Ditmarsch describes in his blog post “ [Migrate to new vCenter Server while using dvSwitches](http://virtualkenneth.com/2012/10/19/migrate-to-new-vcenter-server-while-using-dvswitches/)” how to migrate from a vCenter 4 server with a VDS switch to a new vCenter 5 server. This can be a risky and time consuming task task.

vSphere 5.1 supports to backup and restore the VDS configuration. This makes it possible to migrate the VDS configuration on a new vCenter  server very easily, without to migrate the VDS first to the vSS on the old vCenter server and on the new vCenter server migrate the vSS to the VDS. 

Here are the steps:

- Upgrade the old vCenter server to version 5.1
- Install a new vCenter 5.1 server and create a datacenter and cluster
- Export the DVS configuration on the old vCenter server
- Disable HA on the old cluster(s)
- Disconnect all the hosts on the old vCenter server
- Import all the hosts  on the new vCenter server. The following warning is displayed and it is safe to ignore the warning:

[![image](images/image_thumb1.png "image")](images/image1.png)

- Import the VDS configuration on the new vCenter server

<table border="0" cellspacing="0" cellpadding="2" width="400"><tbody><tr><td valign="top" width="200"><a href="images/image2.png"><img style="background-image: none; border-right-width: 0px; padding-left: 0px; padding-right: 0px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px; padding-top: 0px" title="image" border="0" alt="image" src="images/image_thumb2.png" width="242" height="186"></a></td><td valign="top" width="200"><a href="https://www.ivobeerens.nl/wp-content/uploads/2012/10/image3.png"><img style="background-image: none; border-right-width: 0px; padding-left: 0px; padding-right: 0px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px; padding-top: 0px" title="image" border="0" alt="image" src="images/image_thumb3.png" width="309" height="184"></a></td></tr></tbody></table>

- Remove the disconnected hosts on the old vCenter server

After the VDS import, the warning will disappear and the VDS configuration is migrated to the new vCenter server.

**More information**

[VMware vSphere 5.1 – Network Config Backup and Restore video](http://youtu.be/cfjeHzvsrr0)



