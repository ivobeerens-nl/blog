---
author: Ivo Beerens
categories:
- patch
- Update
- vCenter Server Appliance
- vcsa
date: "2015-07-30T11:26:47Z"
guid: http://www.ivobeerens.nl/?p=3927
id: 3927
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- patch
- update
- vcenter server appliance
- vcsa
title: The new way to patch the vCenter Server Appliance 6
url: /2015/07/30/the-new-way-to-patch-the-vcenter-server-appliance-6/
---

The patching process in vCenter Server Appliance (vCSA) version 6 is changed from previous versions. It is not possible anymore to use the Virtual Appliance Management Interface (VAMI) and update the appliance using the User Interface. The new way to patch the vCenter Server Appliance involves the following steps:

- Download the patch from the VMware Patch Download Center, [link](https://my.vmware.com/group/vmware/patch).
- Choose vc and select version 6.x
- Download the latest patch ISO

[![1_patch](http://localhost/wp-content/uploads/2015/07/1_patch-300x207.png)](http://localhost/wp-content/uploads/2015/07/1_patch.png)

- Attach the \*.ISO to the vCenter Server Appliance.
- Open a console session or SSH (SSH must be enabled) to the appliance. In the console session press ALT + F1 and login.

[![vcsa](http://localhost/wp-content/uploads/2015/07/vcsa-300x272.png)](http://localhost/wp-content/uploads/2015/07/vcsa.png)

- Stage the ISO using the following command

```powershell  
software-packages stage –iso –acceptEulas  
```

- See the staged content

```powershell  
software-packages list –staged  
```

- Install the staged content

```powershell  
software-packages install –staged  
```

- Reboot the appliance

```powershell  
shutdown reboot -r  
```

- After the reboot check the new vCenter Server Appliance build version

[![vcsa version](http://localhost/wp-content/uploads/2015/07/vcsa-version-300x213.png)](http://localhost/wp-content/uploads/2015/07/vcsa-version.png)

The easy updating process that was used in the vCenter Server Appliance 5.x is gone. The new update process involves more manually steps. We hoping that the easy updating will return in further releases of the vCenter Server Appliance.
