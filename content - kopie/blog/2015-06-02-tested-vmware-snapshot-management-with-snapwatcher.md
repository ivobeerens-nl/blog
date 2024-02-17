---
author: Ivo Beerens
categories:
- Reviews
- VMware
- vpshere 5
date: "2015-06-02T09:56:23Z"
guid: http://www.ivobeerens.nl/?p=3731
id: 3731
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- admin
- Snapshot
- tool
- VMware
- vSphere
title: 'Tested: VMware snapshot management with Snapwatcher'
url: /2015/06/02/tested-vmware-snapshot-management-with-snapwatcher/
---

To monitor and manage VMware Virtual Machine Snapshots Opvizor has released a tool called Snapwatcher. As consultant I see often that admins don’t have an overview of all the snapshots that exists in their environment. The main concerns with Virtual Machine snapshots are:

- Snapshots are created and forgot to remove
- Snapshots can very quickly grow in size
- Snapshots filling datastore space
- Delta files may cause decreased Virtual Machine and host performance

In this review Opvizor Snapwatcher is tested. With the Snapwatcher tool it is possible to centrally monitoring and managing snapshots one on more more vCenter server environments.

### **Installation**

The installation of Snapwatcher is simple. Before installing make sure the requirements are met:

- Windows Installer 4.5
- Microsoft .NET Framework 4 (x86 and x64)
- VMware vCenter 4.1 or higher

Download and installation the Snapwatcher application. The installation downloads the latest bits from opvizor.com and installs Snapwatcher.

![1_Install](http://localhost/wp-content/uploads/2015/05/1_Install-300x171.png)[![New Update](http://localhost/wp-content/uploads/2015/06/New-Update-300x139.png)](http://localhost/wp-content/uploads/2015/06/New-Update.png)

Every time Snapwatcher is started it checks for the latest updates. So Snapwather is always up-t0-date.

### **Configuration**

The first configuration step is adding one or more vCenter Servers:

[![add vcenter](http://localhost/wp-content/uploads/2015/05/add-vcenter1-300x163.png)](http://localhost/wp-content/uploads/2015/05/add-vcenter1.png)

After adding the vCenter Server(s), thresholds on warning and error levels can be set, for example:

- Size and age of the snapshot
- Size and percentage of the datastore
- Amount of snapshots for a Virtual Machine

[![thresholds](http://localhost/wp-content/uploads/2015/05/thresholds-300x206.png)](http://localhost/wp-content/uploads/2015/05/thresholds.png)

### **Monitor**

The dashboard is divided in seperate windows. The screenshot below lists the dabboard with all the 5 windows:

[![dashboard](http://localhost/wp-content/uploads/2015/06/dashboard-300x157.png)](http://localhost/wp-content/uploads/2015/06/dashboard.png)

Each window can be resized and re-ordered. The 5 windows displays the following information:

1\. **Overview of the 5 largest snapshots**. The amount of snapshots displayed is configurable.

2\. **Snapshot Disk Waste History (GB)**. Displays how much disk space is wasted over a period of time.

3\. **Overview of all the snapshot**. All the snapshots are listed with there status. Snapshots can be sorted on VM or snapshot name, description, status, Size (GB) and created Date. Actions can performed against snapshots such as delete, fix it and exclude.

4\. **General overview information**. Display information about the number of vCenters, ESXi servers, VMs, VMs with snapshots added, the total snapshots and snapshot size.

[![general info](http://localhost/wp-content/uploads/2015/05/general-info-300x116.png)](http://localhost/wp-content/uploads/2015/05/general-info.png)

5\. **Work History**. Displays information about the deleted snapshots and sizes.

### **Manage**

From the dashboard the following actions can be performed against snapshots:

[![Buttons](http://localhost/wp-content/uploads/2015/06/Buttons.png)](http://localhost/wp-content/uploads/2015/06/Buttons.png)

**Refresh:** Refreshes the dashboard and perform an updated inventory of the snapshots.

**Delete**: Remove the snapshot from the VM.

[![delete](http://localhost/wp-content/uploads/2015/06/delete-300x98.png)](http://localhost/wp-content/uploads/2015/06/delete.png)

**Exclude**: Snapshots can be excluded in the dashboard from displaying. This can be handy for template VM with snapshots or VMware Horizon View Linked Clones.

**Fix It**: Fix It repairs broken snapshots are snapshots that are not managed by the vCenter Server but are still getting used by the Virtual Machine. In the vSphere Web/Client this status is showed as “Virtual Machine disks consoldition is needed”. In Snapwatcher the status is invalid.

[![lx250](http://localhost/wp-content/uploads/2015/05/lx250-300x23.png)](http://localhost/wp-content/uploads/2015/05/lx250.png) [![01 Snapshot](http://localhost/wp-content/uploads/2015/06/01-Snapshot-300x50.png)](http://localhost/wp-content/uploads/2015/06/01-Snapshot.png)

### **Licensing**

When the trail period (7 days) is expired it is still possible to use Snapwatcher. The following Enterprise Edition features will not work when the trail period is over:

- Fix broken and inconsistent snapshots with our patent pending technology
- Ignore certain VM snapshots
- Track your VMware snapshot history

### **Conclusion**

Opvizor Snapwatcher is a great tool for a VMware admin to centrally monitor and manage all the snapshots that exists in there VMware environment. Want to try Snapwatcher? Use this [link](http://try.opvizor.com/snapwatcherent/).
