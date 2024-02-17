---
author: Ivo Beerens
categories:
- hyper
- Hyper-V
- scvmm
date: "2014-07-08T08:40:35Z"
guid: http://www.ivobeerens.nl/?p=2863
id: 2863
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hyper-v
- scvmm
title: Remove an orphaned VM from SCVMM
url: /2014/07/08/remove-an-orphaned-vm-from-scvmm/
---

During a migration of a VM from a different cluster the job failed in SCVMM.

[![image](http://localhost/wp-content/uploads/2014/07/image_thumb.png "image")](http://localhost/wp-content/uploads/2014/07/image.png)

The status of the VM in SCVMM Virtual Machine State is still “Starting”.

[![image](http://localhost/wp-content/uploads/2014/07/image_thumb2.png "image")](http://localhost/wp-content/uploads/2014/07/image2.png)

In SCVMM I was unable to stop, repair or delete the VM. When looking on the Hyper-V host, the VM didn’t exist in Failover Cluster Manager or Hyper-V manager. After some troubleshooting I was able to use the following PowerShell command to remove the orphaned VM in SCVMM:

<font face="Courier New">Import-Module VirtualMachineManager</font>

<font face="Courier New">Get-VM -VMMServer **VMMSERVER** –Name “**VMNAME**" | Remove-VM -Force</font>

Replace the **VMMSERVER** and **VMName** in the PowerShell syntax with your own names
