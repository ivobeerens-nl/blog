---
author: Ivo Beerens
categories:
- vDR
- VMware Data Recovery
date: "2011-09-06T13:02:45Z"
guid: http://www.ivobeerens.nl/?p=1042
id: 1042
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- vDR
- VMware Data Recovery
title: Things to know before implementing VMware Data Recovery (vDR) 2.0
url: /2011/09/06/things-to-know-before-implementing-vmware-data-recovery-vdr-2-0/
---

<span style="color: #000000;">VMware Data Recovery (vDR) is an appliance to backup, storage, and recovery of virtual machines and files within the virtual environment. The new version 2.0 has the following enhancements:</span>

> <span style="color: #000000;">– VMware Data Recovery 2.0 is now a fully 64-bit virtual appliance.</span>
> 
> <span style="color: #000000;">– Email reports. VMware Data Recovery 2.0 makes it possible to generate and email reports, in a fully automated fashion, to an administrator following the completion of a backup.</span>
> 
> <span style="color: #000000;">– Better deduplication Performance</span>
> 
> <span style="color: #000000;">– Job Suspension. VMware Data Recovery enables users to suspend individual jobs from continuing to run by right-clicking on the backup job and selecting “Suspend Future Tasks.”</span>
> 
> <span style="color: #000000;">– Advanced Options such as Change the number of days between automated integrity checks, Specify the day of the week on which the automated integrity check is run and Exclude or include backup of swap partitions or page data.</span>
> 
> <span style="color: #000000;">– Windows </span><span style="color: #000000;">pagefile and Linux swap partitions are automatically excluded from backup by default.</span>
> 
> <span style="color: #000000;">– If the maintenance window closes before an integrity check or reclaim operation is completed, the datastore is not locked as it was in prior releases. This enables backups to continue working even if maintenance is not completed. If, however, damaged restore points are detected, the deduplication datastore will be locked until the damaged restore points are deleted.</span>
> 
> <span style="color: #000000;">– Issues resolved found in vDR 1.2.1:</span>
> 
> <span style="color: #000000;">• CIFS target handling and resilience  
> • Incremental RDM backup  
> • Backups failing with “not enough disk space” errors  
> • Backups failing with “disk full” error despite free space being available</span>

### Before implementing vDR 2.0 consider the following things:

<span style="color: #000000;">– VMware Data Recovery is available in the following vSphere 5 editions: Essentials plus, Standard, Enterprise and Enterprise Plus.</span>

<span style="color: #000000;">– It is possible to full </span><span style="color: #000000;">disaster recovery even when there isn’t any vCenter server available for example because it was installed as VM. </span><span style="color: #000000;">Follow these steps:</span>

> <span style="color: #000000;">– Connect directly to a ESXi server with the vSphere client</span>
> 
> <span style="color: #000000;">– Install the VMware Data Recovery appliance</span>
> 
> <span style="color: #000000;">– Install the VMware Data Recovery client</span>
> 
> <span style="color: #000000;">– Connect to the VMDK, NFS or CIFS share used as deduplication store(s)</span>
> 
> <span style="color: #000000;">– Message appears to import the “old” configuration:</span>
> 
> [<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2011/09/image_thumb7.png "image")</span>](http://localhost/wp-content/uploads/2011/09/image7.png)
> 
> <span style="color: #000000;">– Select “yes” to import the “old” configuration</span>
> 
> <span style="color: #000000;">– Now the configuration is back, you are ready to restore all the VMs </span>

<span style="color: #000000;">– Each backup appliance can protect a total of 100 Virtual Machines. If you want more VMs to backup add an extra backup appliance.</span>

<span style="color: #000000;">– Each instance of vCenter Server can support up to ten Data Recovery backup appliances.</span>

<span style="color: #000000;">– support deduplication stores that are up to one terabyte in size and each backup appliance is limited to using two deduplication stores per appliance ( 1 TB on VMDKs and RDMs and 500 GB on CIFS network shares). </span>

<span style="color: #000000;">– vDR requires an absolute minimum of 10 GB of free space per store for indexing and restore point processing. Due to this seize the stores not smaller as 50 GB.</span>

<span style="color: #000000;">– For initial setup seize the deduplication store space equal to the amount of used disk space on all the VMs being protected.</span>

<span style="color: #000000;">– Use VMDK’s as deduplication store use thick provisioning eager zeroed for the best performance.</span>

<span style="color: #000000;">– Place the deduplication store(s) on storage device on another location.</span>

<span style="color: #000000;">– Using CIFS shares as deduplication store avoid stores on servers with multiple roles or/and services and in a VM.</span>

<span style="color: #000000;">– CIFS shares with passwords limited to 64 characters or less. CIFS share passwords must conform to the Latin 1(ISO 8859-1) standard. Double-byte characters are not supported.</span>

<span style="color: #000000;">– NFS is only supported as a deduplication store format if the share is presented by an ESX/ESXi Server and the VMDK is assigned to the Data Recovery appliance.</span>

<span style="color: #000000;">– All the vDR appliances are managed separately.</span>

<span style="color: #000000;">– Hardware version 7 of higher is needed for using Changed Block Tracing (CBT). Upgrade the hardware version 4 VMs.</span>

<span style="color: #000000;">– Windows pagefiles (pagefile.sys) file and the </span><span style="color: #000000;">Linux swap partition is not backed up. </span>

<span style="color: #000000;">– VMware Data Recovery uses Microsoft Windows Volume Shadow Copy Service (VSS) quiescing ( point-in-time copies).</span>

<span style="color: #000000;">– Here’s an overview of the Guest Operating Systems and the quiescing method:</span>

<span style="color: #000000;">[![image](http://localhost/wp-content/uploads/2011/09/image_thumb8.png "image")](http://localhost/wp-content/uploads/2011/09/image9.png)</span>

<span style="color: #000000;">– Application consistent quiescing of Windows 2008 virtual machines is only available when those virtual machines are created in vSphere 4.1 and later. Virtual machines created in vSphere 4.0 can be updated to enable application consistent quiescing, as described in Enable Windows 2008 Virtual Machine Application Consistent Quiescing.</span>

<span style="color: #000000;">– Because Data Recovery uses VSS, Data Recovery can create snapshots while ensuring application consistency. This means that applications write to disk any important data that is currently in memory, making sure that a later restore of that virtual machine can restore the application back into a consistent state.</span>

<span style="color: #000000;">– A maximum of 8 virtual machines can be backed up simultaneously. Default only 14 SCSI disks can be hot-added. For example when backup 8 VMs with three disks, the hot-add can only hot-add 14 disks, the other disks are backed up over the network. </span><span style="color: #000000;">Add an extra dummy disk (1MB) for every SCSI adapter in the vDR appliance configuration so that the hot-add has enough room.</span>

<span style="color: #000000;">– vDR does not support: </span>

> <span style="color: #000000;">– Backing up virtual machines that are protected by VMware Fault Tolerance,- </span>
> 
> <span style="color: #000000;">– Backing up virtual machines with 3rd party multi-pathing enabled where shared SCSI buses are in use</span>
> 
> <span style="color: #000000;">– Raw device mapped (RDM) disks in physical compatibility mode in virtual machines to be backed up</span>
> 
> <span style="color: #000000;">– Multiple backup appliances on a single host</span>
> 
> <span style="color: #000000;">– </span><span style="color: #000000;">Backup of virtual machine disks that are marked as Independent</span>
> 
> <span style="color: #000000;">– Backup of Storage Virtual Appliances (SVAs)</span>

<span style="color: #000000;">**–** vDR is intent for SMB customer. When using more than one vDR appliance it’s difficult to manage. </span><span style="color: #000000;">If you want more robust solution look 3e party software for example at Veeam Backup and Recovery or Trilead VM Explorer.</span>

### **More information on VMware Data Recovery 2.0**:

– [What’s New in VMware Data Recovery 2.0](http://www.vmware.com/files/pdf/techpaper/Whats-New-VMware-Data-Recovery-20-Technical-Whitepaper.pdf)
