---
title: "Things to consider when upgrading to vSphere 4.1"
date: "2010-08-11T09:10:49.000Z"
categories: 
  - "upgrade"
  - "vmware"
tags: 
  - "scripted"
  - "vcenter"
  - "vmware"
  - "vsphere"
  - "vsphere-4-1"
---

The new vSphere 4.1 release offers a lot of new cool features and enhancements. [Here’s a list What’s New in vSphere 4.1.](http://www.vmware.com/support/vsphere4/doc/vsp_41_new_feat.html) When upgrading to vSphere 4.1 there are a couple of things to think about before starting:

- Make sure your systems and components are supported, check the [Hardware Compatibility Guide](http://www.vmware.com/resources/compatibility/search.php).
- Verify that other products are compatible with vSphere 4.1. For example VMware View 4 is not supported on vSphere 4.1. VMware View composer does not support 64-bit operating systems. 
- vCenter 4.1 server requires a 64-bit OS. 32-bit Operating Systems are not supported anymore for vCenter 4.1 server.
- vSphere 4.1 and its subsequent update and patch releases are the last releases to include both ESX and ESXi hypervisor architectures. Future major releases of VMware vSphere will include only the VMware ESXi architecture. For this reason, **VMware recommends that deployments of vSphere 4.x utilize the ESXi hypervisor architecture**. When migrate to ESXi all the script and programs (such as hardware monitoring agents and backup agents), that uses the Service Console needs to replaced. More information can be the following links [ESX4.1 is the last ESX what do i do now](http://blogs.vmware.com/vsphere/2010/07/esx-41-is-the-last-esx-what-do-i-do-now.html) and in the [ESXi41 Migration Guide](http://www.vmware.com/files/pdf/techpaper/VMW-ESXi41-Migration-Guide.pdf).
- vSphere 4.1 support scripted installation for ESXi. **You cannot use scripted installation to install ESXi to a USB device!** Here are some good links for scripted ESXi 4.1 installations:  **Kenneth van Ditmarsch**, [Setting up vSphere ESXi 4.1 scripted installation](http://virtualkenneth.com/2010/07/21/setting-up-vsphere-esxi-4-1-scripted-installation/), **Kendrick Coleman**, [ESX 4.1 Kickstart install](http://kendrickcoleman.com/index.php?/Tech-Blog/esxi-41-kickstart-install-wip.html), **Billhill**, [Setting up vSphere ESX 4.1 scripted installation from Ubuntu](http://communities.vmware.com/blogs/vmwareinsmb/2010/07/13/esxi-41-scripted-installation-via-pxe-and-kickstart) and [Deploy ESXi 4.1 using Scripted install feature](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1022263 ).
- ESXi comes in two editions, the vSphere Hypervisor (free version) with limited features and the enterprise ESXI.
- The VMware Knowledgebase has best practices for installing and upgrading vSphere 4.1. [Installing ESX 4..1 and vCenter 4.1 best practices]( http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1022101) and [Upgrading to ESX 4.1 and vCenter 4.1 best practices](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1022104).
- Get yourself familiar with tools as **PowerCLI**, **vCLI** and the **VMware Management Assistant (vMA).**These tools helps you to automate, configure  and troubleshoot vSphere 4.1 environments. More information can be found on the following links [vCLI](http://www.vmware.com/support/developer/vcli/), [PowerCLI](http://www.vmware.com/support/developer/PowerCLI/index.html) and [vMA](http://www.vmware.com/support/developer/vima/).
- Before upgrading check the Knowlegde Base from VMware for issues with  vSphere 4.1. For example [Upgrading vCenter Server 4.0 to 4.1 fails with the error: Exception Thrown while executing SQL script](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1025139).

\[ad#verticaal\]
