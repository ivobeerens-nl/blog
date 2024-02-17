---
author: Ivo Beerens
categories:
- vSphere
date: "2018-09-07T11:06:31Z"
firstpublish:
- "1"
guid: https://www.ivobeerens.nl/?p=6167
id: 6167
image: /wp-content/uploads/2018/09/1-3.png
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- PowerCLI
- VMware
- vmware tools
title: VMware Tools 10.3.0 recalled, check you&#8217;re vSphere environment!
url: /2018/09/07/vmware-tools-10-3-0-recalled-check-youre-vsphere-environment/
---

Yesterday VMware released a Knowledge Base article that VMware Tools version 10.3.0 is recalled because issues with the VMXNET3 network driver for Windows on ESXi 6.5. The issues can cause a Purple Diagnostic Screen (PSOD) or guest network connectivity loss. Because of these issues, VMware Tools 10.3.0 is recalled and no longer available.

**Update: September 12, 2018**: VMware Tools 10.3.2. is released that fixes the VMXNET3 issue. More information can be found here, [link](https://t.co/QsI8XZuuRa).

Action is required if VMware Tools 10.3.0 is deployed and the following is true:

- vSphere ESXi 6.5 hosts
- VM Hardware Version 13
- Windows 8/Windows Server 2012 or higher guest OSes

If this is the case uninstall VMware Tools 10.3.0 and reinstall VMware Tools 10.2.5 from the VMware Downloads page, [link](https://my.vmware.com/web/vmware/details?downloadGroup=VMTOOLS1025&productId=614). For other configurations, **no immediate action is required**.

I created a simple PowerCLI script to identify VMware Tools version 10.3.0 and display the Hardware Version and Operating System. With this script you can do quick check if you’re vSphere 6.5 environment contains VMware Tools 10.3.0 with Hardware Version 13 and Windows 8/Windows 2012 or higher VMs.

[![](http://localhost/wp-content/uploads/2018/09/1-3-300x55.png)](http://localhost/wp-content/uploads/2018/09/1-3.png)

The script ‘”identVMwaretools.ps1″ can be found on my GitHub repository, [link](https://github.com/ibeerens/PowerCLI). The KB can be found here, [link](https://kb.vmware.com/s/article/57796).
