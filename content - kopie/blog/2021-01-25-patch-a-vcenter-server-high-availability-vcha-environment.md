---
author: Ivo Beerens
categories:
- Uncategorized
date: "2021-01-25T21:08:57Z"
guid: https://www.ivobeerens.nl/?p=7865
id: 7865
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- vCenter Server
- VMware
title: Patch a vCenter Server High Availability (VCHA) environment
url: /2021/01/25/patch-a-vcenter-server-high-availability-vcha-environment/
---

Last week I tried to patch a vCenter Server High Availability (VCHA) 7 cluster environment. I read the documentation and the procedure described looks still the same as in version 6.x. First patch the witness node, then the passive node, failover the active node, and patch the passive node using the *software-packages* tool. The whole process is described in this [link](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vcenter.upgrade.doc/GUID-C27CD7DF-AB52-4A77-A6A6-A966498D5CA0.html).

When I tried to stage the ISO on the witness node the following error occurred:

> You can not patch a vCenter Server appliance in a vCenter HA cluster. **resolution**: You must remove the vCenter HA configuration, apply patches to vCenter Server appliance, and then reconfigure your vCenter HA deployment.
> 
> [![](http://localhost/wp-content/uploads/2021/01/1-300x63.jpg)](http://localhost/wp-content/uploads/2021/01/1.jpg)

So I removed the vCenter Server HA cluster configuration and patched the single vCenter Server Appliance.

[![](http://localhost/wp-content/uploads/2021/01/2-300x188.jpg)](http://localhost/wp-content/uploads/2021/01/2.jpg)

After the patching of the single VCSA, I redeployed the VCHA cluster again.

**Conclusion**: The vCenter Server HA cluster documentation still has the VCHA 6 update procedure documented that does not work anymore. I will update this blog article if there is more information available.
