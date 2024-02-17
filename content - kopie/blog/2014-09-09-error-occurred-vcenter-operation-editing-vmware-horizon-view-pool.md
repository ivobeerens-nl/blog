---
author: Ivo Beerens
categories:
- VMware Horizon VIew
- VMware View
date: "2014-09-09T12:55:05Z"
guid: http://www.ivobeerens.nl/?p=2999
id: 2999
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Error
- Horizon View
- VMware
title: Error occurred during vCenter operation when editing a VMware Horizon View
  pool
url: /2014/09/09/error-occurred-vcenter-operation-editing-vmware-horizon-view-pool/
---

When editing a VMware Horizon desktop pool in some situations the server error ‘Error occurred during vCenter operation’. appears.

[![1](http://localhost/wp-content/uploads/2014/09/1.png)](http://localhost/wp-content/uploads/2014/09/1.png)

The error hasn’t any useful information that says what is wrong. When this error occurs the vCenter Server is unable to find one or more objects listed in the desktop pool. When changing datacenter, cluster or host settings in vCenter the desktop pool must be updated to. To resolve this error open the desktop pool, select the vCenter settings tab an check or update the Parent VM, Snapshot, Host or cluster, Resource pool and datastores. Also check if the ESXi host with local storage are not in maintenance mode! After updating these settings the error must be gone.

[![2](http://localhost/wp-content/uploads/2014/09/2.png)](http://localhost/wp-content/uploads/2014/09/2.png)
