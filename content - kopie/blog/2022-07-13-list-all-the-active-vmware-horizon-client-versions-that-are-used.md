---
author: Ivo Beerens
categories:
- Uncategorized
date: "2022-07-13T08:20:56Z"
guid: https://www.ivobeerens.nl/?p=8375
id: 8375
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- VMware Horizon
title: List all the active VMware Horizon client versions that are used
url: /2022/07/13/list-all-the-active-vmware-horizon-client-versions-that-are-used/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

Before upgrading a VMware Horizon environment I want to known what VMware Horizon Client versions are in use. Just to be sure that the VMware Horizon clients are supported when upgrading to a new VMware Horizon version.

[![](http://localhost/wp-content/uploads/2022/07/1-300x135.jpg)](http://localhost/wp-content/uploads/2022/07/1.jpg)

Another use-case is to identify the VMware Horizon Client versions that are in use for security releated issues. In the VMware Horizon Administrator you can allow what VMware Horizon client versions are able to connect.

The following script displays all the VMware Horizon sessions and the VMware Horizon client version that is used to connect to the VMware Horizon environment.

Make sure that the VMware.HV.Helper module is installed ([Link](https://github.com/vmware/PowerCLI-Example-Scripts)).

```powershell  
&amp;lt;#  
.SYNOPSIS  
 HorizonClient.ps1.ps1  
.VERSION  
 1.0  
.DESCRIPTION  
 List all the Connection and displays the VMware Horizon client version.  
.NOTES  
 Author(s): Ivo Beerens  
 Requirements:  
 Make sure the VMware.HV.Helper module is installed, see: https://github.com/vmware/PowerCLI-Example-Scripts  
 Copy the VMware.Hv.Helper to the module location.  
.EXAMPLE  
 PS&amp;gt; ./HorizonClient.ps1  
\#&amp;gt;

\# Variables  
$connectionserver = ‘srv-con-01’  
$domain = ‘lab.local’  
$date = Get-date -UFormat "%d-%m-%Y"  
$output = "C:\\Temp\\horclients-$date.csv"

\# Import module  
Import-Module VMware.Hv.Helper

Write-Output "", "Connecting to the Horizon Connection Server"  
Connect-HVServer -Server $connectionserver -domain $domain

\# List all Users and clients with the Horion client the are running  
$localsessioninfo = (get-HVlocalsession).Namesdata | Select-Object UserName, MachineOrRDSServerName, AgentVersion, DesktopPoolCN, ClientType, ClientAddress, ClientName, ClientVersion, SecurityGatewayDNS, SecurityGatewayAddress | Sort-Object ClientVersion

\# Export the output to a grid and CSV file  
$localsessioninfo | Out-GridView -Title ‘VMware Horizon Client versions’  
$localsessioninfo | export-csv $output -Force -NoTypeInformation

Disconnect-HVServer \* -Confirm:$false  
```

[![](http://localhost/wp-content/uploads/2022/07/Client-versions-300x68.jpg)](http://localhost/wp-content/uploads/2022/07/Client-versions.jpg)

This script (HorizonClients.ps1) can be found on my GitHub repo ([Link](https://github.com/ibeerens/VMware-Horizon))
