---
author: Ivo Beerens
categories:
- ESXi
- PowerCLI
- Powershell
- VMware
date: "2014-12-17T10:28:56Z"
guid: http://www.ivobeerens.nl/?p=3227
id: 3227
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:2;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
tags:
- esxi
- PowerCLI
- Powershell
- vib
- VMware
title: VIBSearch Finding VIB versions
url: /2014/12/17/vibsearch-finding-vib-versions/
---

VIBSearch is a simple PowerShell script with a GUI that will search for a specified VIB or all the VIBS installed on the ESXi hosts. A VIB stands for vSphere Installation Bundle (VIB). VIBs are used to package and distribute ESXi software such as drivers. The GUI is designed with SAPIEN PowerShell Studio 2014.

With VIBSearch it is easily to verify that all the ESXi host in the cluster have the same VIB versions installed. VIBSearch can be used for example to easily identify the HP-AMS driver version on all the ESXi hosts.

**Requirements**

VIBSearch is tested with:

- PowerShell 5
- The latests PowerCLI modules
- For the Out-GridView cmdlet, PowerShell ISE is needed. Install ISE by using the following PowerShell commands: 
    - Import-Module ServerManager
    - Add-WindowsFeature PowerShell-ISE

**Installing and executing VIBSearch**

- Download VIBSearch.txt, [link](https://www.dropbox.com/s/fevtlnlm3xdt0du/VIBSearch.ps1?dl=0)
- Open PowerShell and execute: 
    - Set-ExecutionPolicy unrestricted
    - ./vibsearch.ps1

After executing the script the following GUI appears:

[![0](http://localhost/wp-content/uploads/2014/12/01.png)](http://localhost/wp-content/uploads/2014/12/01.png)

- To connect enter the FQDN or IP address of the vCenter name (1) and click on Connect (2) button

[![1](http://localhost/wp-content/uploads/2014/12/11.png)](http://localhost/wp-content/uploads/2014/12/11.png)

- A credential window appear, enter the credentials for authenticating (administrator) to the vCenter Server. For a domain login use: **user user@domainname** or **domainname\\username**

[![5](http://localhost/wp-content/uploads/2014/12/5.png)](http://localhost/wp-content/uploads/2014/12/5.png)

- After successfully authenticating to the vCenter Server there are two options to choose: 
    - List All the VIBS: List all the ESXi hosts in the vCenter Server
    - Search VIB: specify a VIB name for example “HP-AMS”

[![6](http://localhost/wp-content/uploads/2014/12/6.png)](http://localhost/wp-content/uploads/2014/12/6.png)

If authentication to the vCenter Server fails the following error is displayed in the PowerShell window:

[![authen](http://localhost/wp-content/uploads/2014/12/authen.png)](http://localhost/wp-content/uploads/2014/12/authen.png)

**Example output:**

HP-AMS VIB versions

[![hpams](http://localhost/wp-content/uploads/2014/12/hpams.png)](http://localhost/wp-content/uploads/2014/12/hpams.png)

Intel NIC VIB “net-igb” versions

[![Intel](http://localhost/wp-content/uploads/2014/12/Intel.png)](http://localhost/wp-content/uploads/2014/12/Intel.png)

NVIDIA VIB versions:

[![nvidia](http://localhost/wp-content/uploads/2014/12/nvidia.png)](http://localhost/wp-content/uploads/2014/12/nvidia.png)

Thanks to Francois-Xavier Cat (@LazyWinAdm) for helping me with the VIBSearch tool.
