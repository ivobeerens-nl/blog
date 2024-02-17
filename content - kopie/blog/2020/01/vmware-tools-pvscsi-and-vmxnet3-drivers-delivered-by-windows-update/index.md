---
title: "VMware Tools pvscsi and vmxnet3 drivers delivered by Windows Update"
date: "2020-01-09T13:20:10.000Z"
categories: 
  - "vmware"
  - "vsphere"
---

Today I was updating a Windows Server 2016 template VM with Windows Updates. During the update, I notice that the pvscsi and vmxnet3 drivers are updated by the Windows Updates process.

[![](images/WIndowsUpdateDrivers-300x106.jpg)](https://www.ivobeerens.nl/wp-content/uploads/2020/01/WIndowsUpdateDrivers.jpg)

In 10.3.10 of VMware Tools, the pvscsi and vmxnet3 drivers available through Windows Update for Windows Server 2016 and Windows Server 2019 Operating Systems. This means that the pvscsi and vmxnet3 drivers are updated as part of the Windows Updating process. This reduces the number of reboots needed.

So make sure that all the Windows Server 2016 and 2019 VMs have at least version 10.3.10 (or higher) of the VMware Tools installed to reduce the number of reboots.
