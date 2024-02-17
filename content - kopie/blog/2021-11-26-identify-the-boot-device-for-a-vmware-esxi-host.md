---
author: Ivo Beerens
categories:
- vSphere 7
date: "2021-11-26T09:31:16Z"
guid: https://www.ivobeerens.nl/?p=8180
id: 8180
image: /wp-content/uploads/2021/11/BootDevice.jpg
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_reddit_counts:
- "8"
ssb_total_counts:
- "8"
tags:
- boot
- SD card
- vSphere 7
title: Identify the boot device for a VMware ESXi host
url: /2021/11/26/identify-the-boot-device-for-a-vmware-esxi-host/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

With vSphere 7 VMware is moving away from supporting SD cards and USB as boot media. ESXi Boot configuration with only SD card or USB drive, without any persistent device, is deprecated with vSphere 7 Update 3. In future vSphere releases, it will be an unsupported configuration!

Move from SD cards and USB devices to local persistent disk(s) such as SATA, SAS (including SATADOM), SSD disks as a boot device for example. The minimum disk size is 32 GB, the recommended size is 128 GB. Another option is to use boot from SAN.

More information can be found here [link](https://kb.vmware.com/s/article/85685).

The general support period for vSphere 6.7 will end on **October 15, 2022.** So make sure to upgrade before October 15, 2022, to VMware vSphere 7.

To identify what boot media (does not work for boot from SAN) is used I created a PowerCLI script that identifies the boot device for every VMware ESXi host in a cluster. After entering the vCenter Server and credentials it will list all the clusters available in the vCenter environment, select the cluster and the boot device per VMWare ESXi host will be identified.

```powershell  
<#  
.SYNOPSIS  
 This script list the boot device for every VMware ESXi host  
.DESCRIPTION  
 VMware is moving away from the support of SD cards and USB drives as boot media.  
 ESXi Boot configuration with only SD card or USB drive, without any persistent device, is deprecated with vSphere 7 Update 3.  
 In future vSphere releases, it will be an unsupported configuration.  
 More information:  
 https://blogs.vmware.com/vsphere/2021/09/esxi-7-boot-media-consideration-vmware-technical-guidance.html  
.NOTES  
 Version: 1.0  
 Author: Ivo Beerens  
 Creation Date: 2021 November  
 Change: Creation  
\#>

\# Import the PowerCLI module  
Import-Module VMware.PowerCLI

\# Variables  
$datefile = ( get-date ).ToString(‘yyyy-MM-dd-hhmmss’)  
$file = New-Item -type file "C:\\Temp\\bootdevices$datefile.csv"  
$vcenterserver = Read-Host "Enter the vCenter server name"

\# Connect to the vCenter Server  
Connect-VIServer $vcenterserver

$cluster = Get-Cluster | Out-GridView -Title "Select the cluster" -OutputMode Single  
$allhosts = $cluster | Get-VMHost | where {$\_.ConnectionState -eq "Connected"}

$result = @()

foreach ($allhost in $allhosts) {  
 $esxcli = Get-EsxCli -V2 -VMHost $allhost  
 $result += $esxcli.storage.core.device.list.invoke() | Where {$\_.IsBootDevice -match "true"} | Select @{N="Cluster";E={$cluster.Name}},@{N="VMhost";E={$allhost.Name}}, Vendor, Model, IsBootDevice, IsLocal, IsSAS, IsSSD, IsUSB, Device  
}

\# Display the output  
$result | FT

\# Export the output to a CSV file  
$result | Export-Csv $file -NoTypeInformation -Force

\# Disconnect the vCenter server session  
Disconnect-VIserver -Confirm:$false  
```

The output will be displayed on the screen and saved to a CSV file.

[![](http://localhost/wp-content/uploads/2021/11/BootDevice-300x45.jpg)](http://localhost/wp-content/uploads/2021/11/BootDevice.jpg)

This script makes it easy to identify the boot devices of every VMware ESXi host in a cluster.
