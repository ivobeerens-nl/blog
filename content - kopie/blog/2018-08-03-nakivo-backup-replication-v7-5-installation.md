---
author: Ivo Beerens
categories:
- NAKIVO
- Reviews
date: "2018-08-03T09:30:22Z"
guid: https://www.ivobeerens.nl/?p=5767
id: 5767
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- backup
title: Review NAKIVO Backup &#038; Replication v7.5 - Installation
url: /2018/08/03/nakivo-backup-replication-v7-5-installation/
---

In this part of the NAKIVO Backup &amp; Replication review I highlight the installation and basic configuration.

For the installation of NAKIVO Backup &amp; Replication you have several options. <span class="il">NAKIVO</span> Backup &amp; Replication can be installed as:

- Windows or Linux installation package
- Virtual Appliance for VMware (OVF)
- In the Amazon AWS cloud
- <span class="il">Directly installed on NAS devices such as QNAP, Synology and NETGEAR</span>

In my test environment I installed NAKIVO Backup &amp; Replication as Virtual Appliance (VA) on my VMware vSphere 6.7 environment. This is the latest available version of VMware vSphere when writing this blog. The installation of the virtual appliance can be deployed using the vSphere Client (HTML5) or the vSphere Web Interface.

[![](http://localhost/wp-content/uploads/2018/07/2-1-300x224.png)](http://localhost/wp-content/uploads/2018/07/2-1.png)

After specifying the name, ESXi host/cluster, storage and selecting the right network, the VA is ready to be deployed. The appliance uses the following resources as VM:

| OS | Ubuntu Linux (64-bit) Virtual Appliance |
|---|---|
| CPU | 2 vCPU |
| Memory | 4 GB |
| Hard Disk 1 | 30 GB |
| Hard Disk 2 | 520 GB (repository) |
| Network Adapter | 1 |

After the deployment the appliance is ready to start. In the console of the Virtual Appliance several settings can be adjusted such as: networking, security (SSH and root password), time and services using a menu interface.

[![](http://localhost/wp-content/uploads/2018/07/3-300x154.png)](http://localhost/wp-content/uploads/2018/07/3.png)

The next step is the basic configuration.

[![](http://localhost/wp-content/uploads/2018/08/1-300x149.png)](http://localhost/wp-content/uploads/2018/08/1.png)

**Network Attached Storage (NAS) Support**

Another test i did is to install NAKIVO Backup &amp; Replication directly on my QNAP NAS. The installation is straight forward. Download the NAKIVO QNAP package and install this using QNAP AppCenter. After the installation you’re ready to perform the basic configuration.

[![](http://localhost/wp-content/uploads/2018/08/1-300x149.png)](http://localhost/wp-content/uploads/2018/08/1.png)

**Basic config**

After the installation is complete, you can log into NAKIVO Backup &amp; Replication by opening the following URL:

https://<IP\_address\_of\_QNAP\_NAS>:4443

[![](http://localhost/wp-content/uploads/2018/08/2-300x151.png)](http://localhost/wp-content/uploads/2018/08/2.png)

The fist time create an user and you’re able to log in. In a three step wizard the following is configured:

- **Inventory**: On what virtual/cloud environment are my VMs running (VMware, Hyper-V or AWS)?
- **Transporter**: That’s the component that performs the actual backup, replication and recovery as well the data compression, deduplication and encryption of the data.
- **Repository**: Where will the data stored.

**Inventory**

Because I have a VMware vSphere environment, I connect to an ESXi or vCenter Server in the inventory tab.

[![](http://localhost/wp-content/uploads/2018/08/6-300x161.png)](http://localhost/wp-content/uploads/2018/08/6.png) [![](http://localhost/wp-content/uploads/2018/08/7-300x160.png)](http://localhost/wp-content/uploads/2018/08/7.png) [![](http://localhost/wp-content/uploads/2018/08/8-300x160.png)](http://localhost/wp-content/uploads/2018/08/8.png)

**Transporter**

The Virtual Appliance acts as transporter. The maximum load is default 6 concurrent tasks. It’s always possible to add extra transporters when needed.

[![](http://localhost/wp-content/uploads/2018/08/9-300x166.png)](http://localhost/wp-content/uploads/2018/08/9.png)

**Repository**

For the repository I use the onboard repository (uses hard disk 2) that is attached to the Virtual Appliance. The onboard repository compression and deduplication is configured by default.

[![](http://localhost/wp-content/uploads/2018/08/10-300x161.png)](http://localhost/wp-content/uploads/2018/08/10.png)

Other repositories options are: CIFS, NFS and Amazon EBS.

**Updating**

When new updates are available they are displayed in the web interface.

[![](http://localhost/wp-content/uploads/2018/08/2-2-300x194.png)](http://localhost/wp-content/uploads/2018/08/2-2.png) [![](http://localhost/wp-content/uploads/2018/08/3-300x103.png)](http://localhost/wp-content/uploads/2018/08/3.png)

For the Virtual Appliance (VA) download the updated installer and upload it the VA (/opt/nakivo/updates) folder. Open the console of the VA and select “Software Update” in the menu. It would be great when the upgrade process of the VA can be automated without any manually actions in feature releases.

This was the last step of the 3 step wizard. After approximately 15 minutes i’m ready with the installation and basic configuration of the Virtual Appliance. I can conclude the following after the installation and basic configuration of NAKIVO Backup &amp; Replication test:

- The installation of the Virtual Appliance and NAS option are simple and can be deployed very fast (minutes) without the need of a extra Windows licensing costs.
- When installing NAKIVO Backup &amp; Replication on a NAS device. There is no need for VM resources or physical hosts which saves money
- Management via done by Web Browser, no software installation is needed
