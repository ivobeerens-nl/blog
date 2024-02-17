---
title: "Error occurred during vCenter operation when editing a VMware Horizon View pool"
date: "2014-09-09T10:55:05.000Z"
categories: 
  - "VMware-horizon-view-2"
  - "VMware-view"
tags: 
  - "error"
  - "horizon-view"
  - "VMware"
author: Ivo Beerens
---

[![1](images/1.png)](images/1.png)

The error hasn't any useful information that says what is wrong. When this error occurs the vCenter Server is unable to find one or more objects listed in the desktop pool. When changing datacenter, cluster or host settings in vCenter the desktop pool must be updated to.  To resolve this error open the desktop pool, select the vCenter settings tab an check or update the Parent VM, Snapshot, Host or cluster, Resource pool and datastores. Also check if the ESXi host with local storage are not in maintenance mode! After updating these settings the error must be gone.

[![2](images/2.png)](images/2.png)



