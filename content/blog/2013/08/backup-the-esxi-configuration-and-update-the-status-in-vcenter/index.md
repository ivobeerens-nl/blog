---
title: "Backup the ESXi configuration"
date: "2013-08-09T08:24:33.000Z"
categories: 
  - "backup"
  - "esxi"
  - "powercli"
tags: 
  - "backup"
  - "esxi-2"
  - "powercli"
author: Ivo Beerens
---

`#Variables`

`$Folder = "D:\Backup\BCK-ESXi"`

`$FolderOld = "D:\Backup\BCK-ESXi\_old"`

`$vc= "vcenterserver-fqdn"`

`# Connect to local vCenter Server`

`Connect-ViServer`

`# Move existing backup files to the old directory`

`Move-Item ($Folder + "\*.tgz") $FolderOld -force -ErrorAction SilentlyContinue`

`# Backkup ESXi configuration`

`Get-VMHost | ForEach-Object {`

 `$_ | Get-VMHostFirmware -BackupConfiguration -DestinationPath $folder`

`}`

`# Disconnect session vCenter`

`Disconnect-VIserver -Confirm:$false`



