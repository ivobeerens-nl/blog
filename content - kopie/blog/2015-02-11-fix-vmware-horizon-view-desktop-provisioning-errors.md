---
author: Ivo Beerens
categories:
- VMware Horizon VIew
date: "2015-02-11T14:32:14Z"
guid: http://www.ivobeerens.nl/?p=3405
id: 3405
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- Horizon View
- VMware
title: Easily fix VMware Horizon View desktop provisioning errors
url: /2015/02/11/fix-vmware-horizon-view-desktop-provisioning-errors/
---

Sometimes you are unable to remove linked clones or stale desktop entries from the VMware Horizon View Administrator. In this example we have a missing VM in the VMware Horizon View Administrator.

[![1](http://localhost/wp-content/uploads/2015/02/1-300x141.png)](http://localhost/wp-content/uploads/2015/02/1.png) [![2](http://localhost/wp-content/uploads/2015/02/2-300x183.png)](http://localhost/wp-content/uploads/2015/02/2.png)

When trying to remove the VM from the VMware Horizon View Administrator the following error is generated:

> Failed to remove VM…… from the View Composer Inventory

To remove the orphaned missing VM, you need to manually, remove the orphaned records from the ADAM and composer database, AD and vCenter Server. The process is described in the following KB:

- Manually deleting linked clones or stale virtual desktop entires KB, [link](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2015112)

Executing the procedure described in the KB can be a risky. VMware has released a new tool (fling) called “ViewDBChk”. The ViewDBChk tool allows administrators to scan and fix provisioning errors that can not be addressed using the VMware Horizon View Administrator. This tool is supported on VMware Horizon View 5.3 and 6.0. Fling tools are not supported by VMware! **For Horizon View 6.1 and later, the ViewDbChk tool is included with your View Connection Server installation**!

More information

Fling ViewDbChk can be found here, [link](https://labs.vmware.com/flings/viewdbchk)
