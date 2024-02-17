---
title: "The new way to patch the vCenter Server Appliance 6"
date: "2015-07-30T09:26:47.000Z"
categories: 
  - "patch"
  - "update"
  - "vcenter-server-appliance"
  - "vcsa"
tags: 
  - "patch"
  - "update-2"
  - "vcenter-server-appliance"
  - "vcsa"
author: Ivo Beerens
---

- Download the patch from the VMware Patch Download Center, [link](https://my.VMware.com/group/VMware/patch).
- Choose vc and select version 6.x
- Download the latest patch ISO

[![1_patch](images/1_patch-300x207.png)](images/1_patch.png)

- Attach the \*.ISO to the vCenter Server Appliance.
- Open a console session or SSH (SSH must be enabled) to the appliance. In the console session press ALT + F1 and login.

[![vcsa](images/vcsa-300x272.png)](images/vcsa.png)

- Stage the ISO using the following command

\[code language="PowerShell"\] software-packages stage --iso  --acceptEulas \[/code\]

- See the staged content

\[code language="PowerShell"\] software-packages list --staged \[/code\]

- Install the staged content

\[code language="PowerShell"\] software-packages install --staged \[/code\]

- Reboot the appliance

\[code language="PowerShell"\] shutdown reboot -r \[/code\]

- After the reboot check the new vCenter Server Appliance build version

[![vcsa version](images/vcsa-version-300x213.png)](images/vcsa-version.png)

The easy updating process that was used in the vCenter Server Appliance 5.x is gone. The new update process involves more manually steps. We hoping that the easy updating will return in further releases of the vCenter Server Appliance.



