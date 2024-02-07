---
author: Ivo Beerens
categories:
- Hyper-V
date: "2012-03-26T14:49:11Z"
guid: http://www.ivobeerens.nl/?p=1444
id: 1444
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hyper-v
- Powershell
title: Identify NICs in Hyper-V 2012
url: /2012/03/26/identify-nics-in-windows-server-8-hyper-v/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

<span style="color: #445864;">In a Hyper-V cluster are normally a lot of NICs involved. Identifying the right can be challenging. It is important to consequently label your network adapters on all the servers in the Hyper-V cluster.</span>

<span style="color: #445864;">In Windows Server 2012 there are PowerShell Cmdlets that can be used for identifying NICs. Once you identified the NIC, rename it to meaningful name. </span><span style="color: #445864;">The PowerShell Cmdlets listed below can be executed on the following versions:</span>

<span style="color: #445864;">– Windows Server 2012 with the Hyper-V role</span>

– Hyper-V Server 2012

<span style="color: #445864;"> </span>

<span style="color: #445864;">Here are three ways listed using PowerShell to identify the NIC in a Windows Server 8 Hyper-V environment.</span>

### Before you begin

<span style="color: #445864;">Execute PowerShell and import the Hyper-V module using the following command:</span>

```
<pre lang="plain">Import-Module Hyper-V
```

### 1. Identify the NIC by connection State

<span style="color: #445864;">Connect one NIC and use the following command:</span>

```
<pre lang="plain">Get-NetAdapter | Select Name, InterfaceDescription, MediaConnectionState | FL
```

<span style="color: #445864;">Look at which NIC is connected and rename the NIC to a meaningful name (listed below)</span>

[![image](http://localhost/wp-content/uploads/2012/04/image9_thumb1.png "image")](http://localhost/wp-content/uploads/2012/04/image91.png)

<span style="color: #445864;">Add the second NIC and execute the command again and rename the name of the NIC. Do this for all NICs</span>

### 2. Identify the NIC using the MAC address

<span style="color: #445864;">When you know the MAC address of the NIC (for example in a HP Flex-10 environment) it can be identified using the following command:</span>

```
<pre lang="plain">Get-NetAdapter | Select Name, InterfaceDescription, MacAddress | FL
```

[![image](http://localhost/wp-content/uploads/2012/04/image17_thumb1.png "image")](http://localhost/wp-content/uploads/2012/04/image171.png)

<span style="color: #445864;">Look at the corresponding MAC address and rename the NIC to a meaningful name (listed below). Do this for all NICs.</span>

### 3. Identify the NIC by PCI bus ID

<span style="color: #445864;">The last option is to identify the NIC by PCI bus ID. The following command list all NICs PCI bus adapter information:</span>

```
<pre lang="plain">Get-NetAdapterHardwareInfo | select Name, InterfaceDescription, DeviceType, 
Busnumber, Devicenumber, Functionnumber | FL
```

[![image](http://localhost/wp-content/uploads/2012/04/image13_thumb1.png "image")](http://localhost/wp-content/uploads/2012/04/image131.png)

<span style="color: #445864;">Look at the corresponding PCI bus and rename the NIC to a meaningful name (listed below). Do this for all NICs.</span>

### Rename the NIC

<span style="color: #445864;">Rename the NIC to a meaningful name, for example, rename the name “**Wired Ethernet Connection** **2**” to “**MGMT-LOM01-VLAN20”** use the following command**:**</span>

```
<pre lang="plain">Rename-NetAdapter “Wired Ethernet Connection 2” –NewName “MGMT-LOM01-VLAN20”
```
