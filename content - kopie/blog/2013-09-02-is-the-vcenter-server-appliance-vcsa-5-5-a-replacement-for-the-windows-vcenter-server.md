---
author: Ivo Beerens
categories:
- vcenter
- vcsa
date: "2013-09-02T10:42:51Z"
guid: http://www.ivobeerens.nl/?p=2423
id: 2423
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- vCenter
- vcsa
title: Is the vCenter Server Appliance (VCSA) 5.5 a replacement for  the  Windows
  vCenter Server?
url: /2013/09/02/is-the-vcenter-server-appliance-vcsa-5-5-a-replacement-for-the-windows-vcenter-server/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

Back in 2012 I wrote a blog post “[What about the VMware vCenter Server Appliance (VCSA) version 5.1](http://localhost/2012/10/22/what-about-vmware-vcenter-server-appliance-vcsa-version-5-1/)”. One of the limitations with VCSA 5.1 was that the embedded vPostgres database only supports 5 hosts and 50 VMs. So it was only supported in test and very small environments.

Now with vSphere 5.5 the the embedded vPostgres database of the vCenter Server Appliance supports 500 hosts and 5000 VMs. This is a great improvement!

Other pros are:

- No Windows and SQL licenses needed
- Easy and quick to install and upgrade

But there are still limitations such as:

- No Linked mode support (requires ADAM (AD LDS)
- VMware Update Manager can’t be installed in the VCSA, additional Windows based VM or physical server needed (Windows license needed)
- vCenter Heartbeat is not supported
- Not all VMware and third party plugins will work

### Conclusion

There is no direct upgrade path from the Windows vCenter Server to the vCenter Server Appliance! To choose between the Windows vCenter Server and the vCenter Server Appliance the following questions for example needed to be answered:

- How many hosts and VMs are planned in a single vCenter server?
- How do I backup and restore the vPostgres database?
- How do I monitor the vCenter Server?
- It is a Linux appliance. Is there knowledge available to troubleshoot?
- Are all my other VMware products and third party products supported?
- Do I need vCenter Heartbeat?
- How do I patch my ESXi hosts?
- Do I need linked mode?
- Are there other tools to install on the vCenter server?

With the improvement of the vPostgres database it can replace the Windows vCenter Server, but it depends on for example the above questions. With vSphere 5.5 the use of the vCenter Server Appliance can be considered in every new design or upgrade path.
