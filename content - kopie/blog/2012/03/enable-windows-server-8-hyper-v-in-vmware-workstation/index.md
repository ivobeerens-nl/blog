---
title: "Enable Windows Server 8 Hyper-V in VMware Workstation"
date: "2012-03-13T21:15:01.000Z"
categories: 
  - "hyper-v"
  - "windows-8"
  - "workstation"
tags: 
  - "hyper-v-2"
  - "windows-8"
  - "workstation"
---

VMware Workstation Technology Preview 2012 is available as download.  The Technology Preview makes it possible for example to install and operate Windows 8 and Windows Server 8 in a VM and the possibility to nest VMs.

I tested the installation of  Windows Server 8 in VMware Workstation TP, enabled the Hyper-V role and run a Windows 7 64-bit VM in Hyper-V. Here are some screenshots (Hyper-V manager and the Windows 7 64  bit running in Hyper-V): 

[![image](images/image_thumb20.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/03/image20.png)

[![image](images/image_thumb21.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/03/image21.png)

To make the above configuration work, add to following options to the end of the VMX file before starting the Windows Server 8 installation:

hypervisor.cpuid.v0 = FALSE
mce.enable = "TRUE"

The VMware Workstation TP VMs are started in debug mode which impacts the performance!  

[![image](images/image_thumb22.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/03/image22.png)

More information can be found here:

\- [VMware Workstation Technology Preview 2012 Overview](http://communities.vmware.com/docs/DOC-18665)

\- [Download](http://communities.vmware.com/community/vmtn/beta/workstationtp2012)

\[ad#banner\]
