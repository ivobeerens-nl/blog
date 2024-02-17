---
author: Ivo Beerens
categories:
- Uncategorized
- VMware
- vSphere
date: "2020-01-09T14:20:10Z"
guid: https://www.ivobeerens.nl/?p=7305
id: 7305
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
title: VMware Tools pvscsi and vmxnet3 drivers delivered by Windows Update
url: /2020/01/09/vmware-tools-pvscsi-and-vmxnet3-drivers-delivered-by-windows-update/
---

Today I was updating a Windows Server 2016 template VM with Windows Updates. During the update, I notice that the pvscsi and vmxnet3 drivers are updated by the Windows Updates process.

[![](http://localhost/wp-content/uploads/2020/01/WIndowsUpdateDrivers-300x106.jpg)](http://localhost/wp-content/uploads/2020/01/WIndowsUpdateDrivers.jpg)

In 10.3.10 of VMware Tools, the pvscsi and vmxnet3 drivers available through Windows Update for Windows Server 2016 and Windows Server 2019 Operating Systems. This means that the pvscsi and vmxnet3 drivers are updated as part of the Windows Updating process. This reduces the number of reboots needed.

So make sure that all the Windows Server 2016 and 2019 VMs have at least version 10.3.10 (or higher) of the VMware Tools installed to reduce the number of reboots.
