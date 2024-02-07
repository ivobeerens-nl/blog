---
author: Ivo Beerens
categories:
- vdp
- VMware Data Protection
- vsphere51
date: "2013-01-18T12:04:45Z"
guid: http://www.ivobeerens.nl/?p=2123
id: 2123
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- vdp
- VMware Data Protection
- vsphere51
title: Windows 2008 R2 VMs fail to backup with VMware Data Protection (VDP)
url: /2013/01/18/windows-2008-r2-vms-fail-to-backup-with-vmware-data-protection-vdp/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

When using VMware Data Protection (VDP) 5.1 and want to backup Windows 2008 R2 VM’s you should disable application-consistent quiescing. On the moment the VADP API doesn’t support Windows 2008 R2 application-consistent quiescing. So be sure that servers that uses a database such as SQL and Exchange are backuped with other third party backup software else the database will be not consistent when restoring!

If you don’t disable application-consistent quiescing the backup of the Windows 2008 R2 will probably fail. I experienced this problem by customers who are using VDP and wanted to backup Windows 2008 R2 VMs.

To disable application quiescing use the following steps (This example is based on the vSphere Client but the vSphere Web client can be used to):

- Shut Down the VM
- Edit the settings of the VM, go to the **Options** tab – go to **General** and click on **Configuration** **Parameters** box

[![image](http://localhost/wp-content/uploads/2013/01/image_thumb4.png "image")](http://localhost/wp-content/uploads/2013/01/image4.png)

- Look if the **disk.EnableUUId** parameter exist. If not Add a new row with this parameter.
- Change the value of the **disk.EnableUUId** parameter to **false**

[![image](http://localhost/wp-content/uploads/2013/01/image_thumb5.png "image")](http://localhost/wp-content/uploads/2013/01/image5.png)

- Click
- Power On the VM

After changing the **disk.EnableUUId** parameter to **false** the backup of the Windows 2008 R2 succeeded with VDP. If you have a lot of VMs you can use PowerCLI to automate this process.
