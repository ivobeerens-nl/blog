---
title: "Windows 2008 R2 VMs fail to backup with VMware Data Protection (VDP)"
date: "2013-01-18T11:04:45.000Z"
categories: 
  - "vdp"
  - "vmware-data-protection"
  - "vsphere51"
tags: 
  - "vdp"
  - "vmware-data-protection"
  - "vsphere51"
---

When using VMware Data Protection (VDP) 5.1 and want to backup Windows 2008 R2 VM’s you should  disable application-consistent quiescing. On the moment the VADP API doesn’t support Windows 2008 R2 application-consistent quiescing. So be sure that servers that uses a database such as SQL and Exchange are backuped with other third party backup software else the database will be not consistent when restoring!

If you don’t disable application-consistent quiescing the backup of the Windows 2008 R2 will probably fail. I experienced this problem by customers who are using VDP and wanted to backup Windows 2008 R2 VMs.

To disable application quiescing use the following steps (This example is based on the vSphere Client but the vSphere Web client can be used to):

- Shut Down the VM
- Edit the settings of the VM, go to the **Options** tab – go to **General** and click on **Configuration** **Parameters** box

[![image](images/image_thumb4.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2013/01/image4.png)

- Look if the **disk.EnableUUId** parameter exist. If not Add a new row with this parameter.
- Change the value of the **disk.EnableUUId** parameter to **false**

[![image](images/image_thumb5.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2013/01/image5.png)

- Click
- Power On the VM

After changing the **disk.EnableUUId**  parameter to **false** the backup of the Windows 2008 R2 succeeded with VDP. If you have a lot of VMs you can use PowerCLI to automate this process.
