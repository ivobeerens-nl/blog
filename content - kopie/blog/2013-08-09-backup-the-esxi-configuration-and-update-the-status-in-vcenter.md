---
author: Ivo Beerens
categories:
- backup
- ESXi
- PowerCLI
date: "2013-08-09T10:24:33Z"
guid: http://www.ivobeerens.nl/?p=2411
id: 2411
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:2;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
tags:
- backup
- esxi
- PowerCLI
title: Backup the ESXi configuration
url: /2013/08/09/backup-the-esxi-configuration-and-update-the-status-in-vcenter/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

I create a simple PowerCLI script that backups all the VMware ESXi host configurations that are connected to a vCenter Server. This script can be scheduled to make for example every week a backup of the ESXi server configs. You can easily customize the script for your own needs.

<div><div>`#Variables`</div><div>`$Folder = "D:\Backup\BCK-ESXi"`</div><div>`$FolderOld = "D:\Backup\BCK-ESXi\_old"`</div><div>`$vc= "vcenterserver-fqdn"`</div><div></div><div>`# Connect to local vCenter Server`</div><div>`Connect-ViServer`</div><div></div><div>`# Move existing backup files to the old directory`</div><div>`Move-Item ($Folder + "\*.tgz") $FolderOld -force -ErrorAction SilentlyContinue`</div><div>`# Backkup ESXi configuration`</div><div>`Get-VMHost | ForEach-Object {`</div><div>`    $_ | Get-VMHostFirmware -BackupConfiguration -DestinationPath $folder`</div><div>`}`</div><div></div><div>`# Disconnect session vCenter`</div><div>`Disconnect-VIserver -Confirm:$false`</div></div><div></div><div></div>
