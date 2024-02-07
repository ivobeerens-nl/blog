---
author: Ivo Beerens
categories:
- upgrade
- vSphere
date: "2010-12-17T14:09:09Z"
guid: http://www.ivobeerens.nl/?p=752
id: 752
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- upgrade
- vpshere
title: Post checks after upgrading to VMware vSphere 4.1
url: /2010/12/17/post-checks-after-upgrading-to-vmware-vsphere-4-1/
---

### <font color="#000000">Memory limits</font>

<font color="#000000">When adding existing VMware ESX servers (for example 3.5) to the VMware vCenter 4.1 server, all the VMs got a memory limit.</font>

[<font color="#000000">![2010-12-10 12h39_01](http://localhost/wp-content/uploads/2010/12/2010-12-10-12h39_01_thumb.jpg "2010-12-10 12h39_01")</font>](http://localhost/wp-content/uploads/2010/12/2010-12-10-12h39_01.jpg)

<font color="#000000">To reset the memory limits to unlimited for all VMs, use the following PowerCLI script:</font>

```
<span style="color: #5f9ea0; font-weight: bold">Connect-VIServer</span><span style="color: #000000"> </span><span style="color: #800000">servername</span><span style="color: #000000">
</span><span style="color: #5f9ea0; font-weight: bold">Get-VM</span><span style="color: #000000"> | </span><span style="color: #5f9ea0; font-weight: bold">Get-VMResourceConfiguration</span><span style="color: #000000"> | </span><span style="color: #5f9ea0; font-weight: bold">Where-Object</span><span style="color: #000000"> {</span><span style="color: #800080">$_</span><span style="color: #000000">.MemLimitMB </span><span style="color: #ff0000">-ne</span><span style="color: #000000"> </span><span style="color: #800000">‘</span><span style="color: #800000">-1‘} </span><span style="color: #800000">| </span><span style="color: #800000">Set-VMResourceConfiguration -MemLimitMB $null
</span>
```

### <font color="#000000">VMware ESX NICs as fixed </font>

<font color="#000000"></font>

<font color="#000000">Already mentioned earlier in the “</font>[<font color="#000000">Change NIC speed and duplex setting to AUTO in ESX4 using PowerCLI”</font>](http://localhost/?p=537)<font color="#000000"> blogpost. The VMware ESX installation set by default each NIC in the VMware hosts to fixed. To change every NIC from fixed to auto negotiate use the following PowerCLI script</font>

```
<span style="color: #5f9ea0; font-weight: bold">Connect-VIServer</span><span style="color: #000000"> </span><span style="color: #800000">servername</span><span style="color: #000000">
</span><span style="color: #5f9ea0; font-weight: bold">Get-VMHostNetworkAdapter</span><span style="color: #000000"> | </span><span style="color: #5f9ea0; font-weight: bold">Set-VMHostNetworkAdapter</span><span style="color: #000000"> </span><span style="font-style: italic; color: #5f9ea0">–AutoNegotiate</span>
```

### <font color="#000000">Active Directory Web Services warnings in the vCenter server event log</font>

<font color="#000000">The following warning is flooding the vCenter event log:</font>

> <font color="#000000">Active Directory Web Services encountered an error while reading the settings for the specified Active Directory Lightweight Directory Services instance. Active Directory Web Services will retry this operation periodically. In the mean time, this instance will be ignored.</font>
> 
> <font color="#000000">Instance name: ADAM\_VMwareVCMSDS</font>
> 
> <font color="#000000">EventID: 1209</font>

<font color="#000000">The Port SSL value is created as a REG\_SZ instead of a REG\_DWORD. To solve this warning open the Windows registry editor (regedt32) and browse to:</font>

- <font color="#000000">HKLM\\System\\CurrentControlSet\\Services\\VMwareVCMSDS\\Parameter </font>
- <font color="#000000">Delete the “Port SSL” value </font>
- <font color="#000000">Create a new ““Port SSL” value as REG\_DWORD and give it the data 636. </font>
- <font color="#000000">Restart the ADM instance </font>
