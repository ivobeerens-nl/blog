---
author: Ivo Beerens
categories:
- NAKIVO
- Reviews
date: "2018-08-16T08:36:40Z"
guid: https://www.ivobeerens.nl/?p=5776
id: 5776
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- backup
title: Review NAKIVO Backup &#038; Replication v7.5 - Backup and Recovery
url: /2018/08/16/review-nakivo-backup-replication-v7-5-backup-and-recovery/
---

In this part of the NAKIVO Backup &amp; Replication review the backup and recovery options will be highlighted.

## **Backup**

To begin with backup and recovery we first need a backup job. Configuring a backup job contains the following five steps:

- **1. VMs**: Select the VMs to backup from the inventory of the vCenter Server or ESXi host.

[![](http://localhost/wp-content/uploads/2018/08/1-2-267x300.png)](http://localhost/wp-content/uploads/2018/08/1-2.png) [![](http://localhost/wp-content/uploads/2018/08/2-3-271x300.png)](http://localhost/wp-content/uploads/2018/08/2-3.png)

- **2. Destination**: Select the destination to store the VMs. Select the onboard repository with deduplication and compression enabled for storage space savings.

[![](http://localhost/wp-content/uploads/2018/08/3-1-268x300.png)](http://localhost/wp-content/uploads/2018/08/3-1.png)

- **3. Schedule**: Create one or more backup schedules

[![](http://localhost/wp-content/uploads/2018/08/4-267x300.png)](http://localhost/wp-content/uploads/2018/08/4.png)

- **4. Retention**: Define the retention period for each Virtual Machine (VM). Each VM will have one or more recovery points were individual files, application object or the the entire VM can be recovered. A Grandfather-Father-Son (GFS) backup rotation scheme can be used.

[![](http://localhost/wp-content/uploads/2018/08/5-269x300.png)](http://localhost/wp-content/uploads/2018/08/5.png)

- **5. Options**: Select the options for the backup job: 
    - ***App-aware mode***: Use this option for applications that require that the data is consistent such as Microsoft SQL and Exchange.
    - ***Change tracking***: Only the blocks that are changed since the last backup will be backup ed. This will increase the backup speed.
    - ***Screenshot verification***: After the backup of each VM it will be recovered (with the network disconnected) and a screenshot will be made after the OS is started. The screenshot will be included in the email notification or in the job report.
    - ***Email notifications***: When the job completes the status is send by Email.
    - ***Transport Mode***: Hot Add, SAN, LAN or automatic can be selected
    - ***Bandwith throttling:*** With bandwidth throttling you can control the amount of bandwidth that is consumed by NAKIVO Backup and Replication.

[![](http://localhost/wp-content/uploads/2018/08/6-1-266x300.png)](http://localhost/wp-content/uploads/2018/08/6-1.png) [![](http://localhost/wp-content/uploads/2018/08/7-1-300x189.png)](http://localhost/wp-content/uploads/2018/08/7-1.png) [![](http://localhost/wp-content/uploads/2018/08/8-1-291x300.png)](http://localhost/wp-content/uploads/2018/08/8-1.png)

The are more options to configure, refer to the following [link](https://helpcenter.nakivo.com/display/NH/Backup+Job+Wizard+for+VMware%3A+Options+Step) for all the options to configure.

In 5 easy wizzard based steps a backup job is be configured.

### **Reports**

There are several reporting functions available such as:

- **Last run report.** Provides the status of the last run backup.
- **Point-in-time report.** Provides data on a particular job run.
- **Job history report.** Provides data on job runs that occurred during a specified time period.
- **Protection coverage report.** Contains information about all VMs and instances protected by backup and/or replication jobs, as well as about all unprotected VMs and instances.

The “last run” report is includes information about the backup such as:

- Summary
- Virtual Machines
- Target Storage
- Alarms &amp; Notifications

This report can be created manually or in the backup job you can specify the email address of one or more recipient(s) were the report will be send to.

[![](http://localhost/wp-content/uploads/2018/08/report-1-213x300.png)](http://localhost/wp-content/uploads/2018/08/report-1.png)

When screenshot verification is used, the screenshot is also included in the report.

## **Restore / Recover**

**Appliance backup**

The configuration of the NAKIVO Backup &amp; Replication server /appliance can be secured by using the Self-backup feature. When something happen with the NAKIVO Backup &amp; Replication server the configuration can be quickly restored on another server.

[![](http://localhost/wp-content/uploads/2018/08/1-7-300x163.png)](http://localhost/wp-content/uploads/2018/08/1-7.png)

After the first backup job is finished there a multiple ways to recover VM data. The following options are available to recover data from the backups:

- **Individual files**. You can recover files or folders directly from compressed and deduplicated repository.
- **Microsoft SQL Server objects.** Enables browsing, searching, and recovering Microsoft SQL Server objects.
- **Microsoft Active Directory objects. E**nables browsing, searching, and recovering Microsoft Active Directory objects**.**
- **Microsoft Exchange objects**. Enables browsing, searching, and recovering Microsoft Exchange emails.
- **Export Backups**. This is called “**Cross-Platform Recovery”** and will be handled in the next paragraph.
- **Flash VM boot**. Enables to run VMware and Hyper-V VMs directly from repository without the need to recover the VMs first.
- **VM recovery from backup**. Full VM recovery. When you recover a VM, a new VM is created and the “old” VM is retained.

[![](http://localhost/wp-content/uploads/2018/08/2-4-264x300.png)](http://localhost/wp-content/uploads/2018/08/2-4.png)

I tested several recover options:

- **Individual files.** Individual files per VM can be restored. The files can be recovered on a server (for example on the same location as deleted), downloaded to the browser or emailed. I tested to recover two PowerShell files from a VM and selected the download to browser option. The files recovery is performed in seconds.

[![](http://localhost/wp-content/uploads/2018/08/2-7-300x178.png)](http://localhost/wp-content/uploads/2018/08/2-7.png) [![](http://localhost/wp-content/uploads/2018/08/3-3-300x155.png)](http://localhost/wp-content/uploads/2018/08/3-3.png)

- **VM recovery from backup**. With this option one or more full VMs are recovered. The original VM will be retained so the recovering VM will not overwrite the original VM. The recovering VM name will append “-recovered” in the end. The recovery is fast.

[![](http://localhost/wp-content/uploads/2018/08/1-5-300x178.png)](http://localhost/wp-content/uploads/2018/08/1-5.png)[![](http://localhost/wp-content/uploads/2018/08/2-8-300x182.png)](http://localhost/wp-content/uploads/2018/08/2-8.png) [![](http://localhost/wp-content/uploads/2018/08/4-1-300x149.png)](http://localhost/wp-content/uploads/2018/08/4-1.png)

- **VM Flash boot.** With the VM Flash boot option it’s possible to boot VMs directly from the compressed and deduplicated repository without recovering the VMs first. This saves time and can be used for example for testing software updates. VM Flash boot uses iSCSI technology to connect VM disks stored in the backup to a target to the ESXi host. In this test I recovered two VMs in isolated network and performed a software update for testing. The changes are not written to the recovery point that i’m using. When i’m finished with testing i can discard the VMs with a single click so that all the changes are lost.

[![](http://localhost/wp-content/uploads/2018/08/1-8-300x191.png)](http://localhost/wp-content/uploads/2018/08/1-8.png) [![](http://localhost/wp-content/uploads/2018/08/2-9-300x191.png)](http://localhost/wp-content/uploads/2018/08/2-9.png) [![](http://localhost/wp-content/uploads/2018/08/3-4-300x192.png)](http://localhost/wp-content/uploads/2018/08/3-4.png) [![](http://localhost/wp-content/uploads/2018/08/4-3-300x192.png)](http://localhost/wp-content/uploads/2018/08/4-3.png)

- **Cross-Platform Recovery.** Cross-Platform Recovery allows exporting virtual disks to other formats such as: 
    - VMDKs for VMware
    - VHD for Hyper-V
    - VDHX for Hyper-V

This allows you to recover VMs in different environments (VMware to Hyper-V and Hyper-V to VMware). In this testI exported a VMware Virtual Machine with two VMDK disks to VHDX disks with the Backup Export Wizard. The “Export backups” wizzard is used and by selecting the VM and recovery point, disks and options to start the export job.

[![](http://localhost/wp-content/uploads/2018/08/1-4-268x300.png)](http://localhost/wp-content/uploads/2018/08/1-4.png) [![](http://localhost/wp-content/uploads/2018/08/3-2-267x300.png)](http://localhost/wp-content/uploads/2018/08/3-2.png) [![](http://localhost/wp-content/uploads/2018/08/2-5-269x300.png)](http://localhost/wp-content/uploads/2018/08/2-5.png)

When the export completed, I created a new VM in Hyper-V Manager and pointed to the restored VDHX disks. Then i was able to start a Hyper-V VM with the exported disks attached. Cross-Platform Recovery can be used for recover VM disks from between hypervisor such as VMware vSphere to Hyper-V and to VMware Workstation and VirtualBox.

[![](http://localhost/wp-content/uploads/2018/08/1-6-300x226.png)](http://localhost/wp-content/uploads/2018/08/1-6.png)

In this part of the NAKIVO Backup &amp; Replication review I highlighted the backup and recovery features. It was a pleasure to test the backup and recovery features because they were easy, quick and they worked out of the box without any troubleshooting skills needed. In the next review I will highlight the replication feature.
