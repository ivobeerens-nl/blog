---
title: "VMware vSphere PowerCLI version 4.1 Update 1 released"
date: "2010-12-02T08:51:14.000Z"
categories: 
  - "powercli"
  - "powershell"
  - "vmware"
tags: 
  - "powercli"
  - "vmware"
---

VMware has released PowerCLI 4.1 Update 1 build 332441. This release of vSphere PowerCLI 4.1 Update 1 introduces the following new capabilities:

>  \* Using the ESX CLI and ESX Top features of VMware vSphere. (experimental)  
>     \* Working with distributed switches and distributed switch port groups.  
>     \* Supporting SCSI controllers.  
>     \* Querying and modifying vCenter Server alarms.  
>     \* Managing advanced vCenter Server settings and Cluster HA advanced options.  
>     \* Waiting for VMware Tools of the specified virtual machines to load.  
>     \* Querying information about disk and disk partitions of hosts.  
>     \* Formatting host disk partitions.  
>     \* Querying the primary HA cluster nodes.  
>     \* Zeroing out virtual machine hard disks.
> 
> In addition, the following changes were made in PowerCLI 4.1 Update 1:
> 
>  \* The DeleteFromDisk parameter of the Remove-VM, Remove-Folder, Remove-HardDisk, Remove-Template, and Remove-VApp cmdlets is now renamed to DeletePermanently.  
>     \* The Set-VMGuestRoute cmdlet was removed for usability and stability reasons. Instead of modifying a route, you can create a new route and delete the old one.

The complete PowerCLI changelog can be found [here](http://www.vmware.com/support/developer/PowerCLI/changelog.html#PowerCLI41U1) and can be downloaded from this [link](http://communities.vmware.com/community/vmtn/vsphere/automationtools/powercli?source=web&cd=1&ved=0CBgQFjAA&url=http://www.vmware.com/go/powershell&rct=j&q=powercli%20download&ei=0Vz3TLz_IoGhOtzn7LMI&usg=AFQjCNGjn3qwmK6abih3q24OXOyj5z0-qA).
