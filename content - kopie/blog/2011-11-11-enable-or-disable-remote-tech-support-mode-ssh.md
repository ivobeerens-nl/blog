---
author: Ivo Beerens
categories:
- PowerCLI
- vpshere
date: "2011-11-11T10:58:48Z"
guid: http://www.ivobeerens.nl/2011/11/11/enable-or-disable-remote-tech-support-mode-ssh/
id: 1117
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- PowerCLI
- vSphere
title: Enable and disable Remote Tech Support mode (SSH)
url: /2011/11/11/enable-or-disable-remote-tech-support-mode-ssh/
---

<font color="#000000"></font>

<font color="#000000">When you start the Remote Tech Support (TSM) service on a VMware ESXi host a warning and the following message will appear:</font>

> <font color="#000000">Remote Tech Support Mode (SSH) for the host … has been enabled</font>

[![image](http://localhost/wp-content/uploads/2011/11/image_thumb1.png "image")](http://localhost/wp-content/uploads/2011/11/image20.png)

<font color="#000000"></font>

<font color="#000000">When the warning appears some Admins get a little nervous. Since VMware ESXi 4.1 Update 2 and VMware ESXi 5 the warning can be suppressed. </font>

<font color="#000000">When starting the Remote Tech Support (TSM) service it is possible to SSH to the ESXi host. </font>

<font color="#000000">The following script can start or stop the Remote Tech Support mode and suppress the warnings on the VMware ESXi hosts.</font>

```
<pre lang="ps">
<#
.SYNOPSIS
  Enable or Disable TSM 
.VERSION
 1.0
.DESCRIPTION
  TSM-SSH Remote Tech Support (SSH) 
.NOTES
  Author(s): Ivo Beerens 
.EXAMPLE
  PS> ./tsm.ps1
#>

Add-PSSnapin vmware.VimAutomation.core -ErrorAction SilentlyContinue

# VMware VirtualCenter server name 
$VCserver = read-host "Enter your vCenter server"
$Username= read-host "Enter the username"
$Password = read-host "Enter password"

# Connect to the vCenter server 
Connect-VIServer $VCserver -User $Username -Password $Password -port 443
 
# Menu
Write-Host "Choose Start or to stop the Remote Tech Support (SSH)service"
Write-Host " 1. Start Remote Tech Support (SSH)"
Write-Host " 2. Stop Remote Tech Support (SSH)"
$response = Read-Host "Select 1 or 2"

if ($response -eq 1){
#Start
get-vmhost | Set-VMHostAdvancedConfiguration -Name "UserVars.SuppressShellWarning" -Value 1
get-vmhost | Get-VMHostService | Where {$_.key -eq "TSM-SSH"} | Start-VMHostService 
}

if ($response -eq 2){
#Stop
get-vmhost | Get-VMHostService | Where {$_.key -eq "TSM-SSH"} | Stop-VMHostService -Confirm:$false
get-vmhost | Set-VMHostAdvancedConfiguration -Name "UserVars.SuppressShellWarning" -Value 0 
}
```
