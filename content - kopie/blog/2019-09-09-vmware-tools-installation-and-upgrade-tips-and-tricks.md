---
author: Ivo Beerens
categories:
- VMware
- VMware Tools
date: "2019-09-09T10:07:08Z"
guid: https://www.ivobeerens.nl/?p=7008
id: 7008
ssb_old_counts:
- a:6:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- PowerCLI
- vmware tools
title: VMware Tools installation and upgrade tips and tricks
url: /2019/09/09/vmware-tools-installation-and-upgrade-tips-and-tricks/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

The VMware Tools package provides drivers (such as VMXNET3, PVSCSI, SVGA etc.) and services that enhance the performance of virtual machines and make several vSphere features easy to use. Here are some tips and tricks when working with VMware Tools:

- An overview of the VMware Tools versions mapping can be found here, [link](https://packages.vmware.com/tools/versions)
- The latest VMware Tools versions can be downloaded from the following links: [link](https://www.vmware.com/go/tools) and [link](https://packages.vmware.com/tools/esx/index.html)
- Within VMware ESXi, the VMware Tools are located under: /vmimages/tools-isoimages
- The latest VMware Tools version 10.3.10 is compatible with ESXi 6.0.0 to 6.7 U3
- To view what VMware Tools components are installed on a Windows operating system: open Regedit and browse to the following location.

\[code language=”text”\]  
HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Classes\\Installer\\Features\\10176710886A59A4C938D6DEE96B37D5  
```

[![](http://localhost/wp-content/uploads/2019/09/Tools_3-300x162.png)](http://localhost/wp-content/uploads/2019/09/Tools_3.png)

Names with a squire or minus are not installed. Another method in Windows 10 for example is going to the Apps &amp; Features and select: modify VMware Tools

- A silent or unattended default installation can be done using the following command. This command does not installed the NSX components:

\[code language=”text”\] Setup64.exe /s /v "/qb REBOOT=R" /l c:\\windows\\temp\\vmware\_tools\_install.log```

[![](http://localhost/wp-content/uploads/2019/09/Tools_1-300x235.png)](http://localhost/wp-content/uploads/2019/09/Tools_1.png)

- Use the ADDLOCAL and REMOVE option to define what components to install. The following command installs all the components expect the Hgfs, SVGA,VSS, AppDefense and the NetworkIntrospection component. This VMware Tools configuration can be used for example for a Horizon View Golden image.

\[code language=”text”\]setup64.exe /s /v" /qb REBOOT=R ADDLOCAL=All REMOVE=Hgfs,SVGA,VSS,AppDefense,NetworkIntrospection"" /l c:\\windows\\temp\\vmware\_tools\_install.log```

[![](http://localhost/wp-content/uploads/2019/09/Tools_2-300x235.png)](http://localhost/wp-content/uploads/2019/09/Tools_2.png)

The following VMware Tools component values can be used:

| **Component Values** | **Component** | **Description** |
|---|---|---|
| **Drivers** | Audio | Audio driver for 64-bit Operating Systems |
|  | BootCamp | Driver for Mac BootCamp Support |
|  | MemCtl | VMware Memory control driver for memory management |
|  | Mouse | VMware mouse driver |
|  | PVSCSI | VMware Paravirtual SCSI adapter |
|  | SVGA | VMware SVGA driver |
|  | Sync | Filesystem Sync driver, which enables backup applications to create application-consistent snapshots. **This driver is used if the guest operating system is earlier than Windows Server 2003. Newer operating systems use the VSS driver.** |
|  | ThinPrint | Driver that enables printers added to the host operating system to appear in the list of available printers in the virtual machine. VMware Tools does not support ThinPrint features for vSphere 5.5 and later. |
|  | VMCI | Virtual Machine Communication Interface driver. This driver allows virtual machines to communicate with the hosts on which they run without using the network |
|  | Hgfs | VMware shared folders driver. Use this driver if you plan to use this virtual machine with VMware Workstation, Player, or Fusion. Excluding this feature prevents you from sharing a folder between your virtual machine and the host system. |
|  | VMXNet | VMware VMXnet networking driver. |
|  | VMXNet3 | Next-generation VMware VMXnet networking driver for virtual machines that use virtual hardware version 7 and higher (ESX(i) 4.x and higher) |
|  | FileIntrospection | NSX File Introspection driver, vsepflt.sys. |
|  | NetworkIntrospection | NSX Network Introspection driver, vnetflt.sys. |
|  | VSS | Driver for creating automatic backups. This driver is used if the guest operating system is Windows Vista, Windows Server 2003, or other newer operating system. Linux and older Windows operating systems use the Filesystem Sync driver. |
|  | AppDefense | VMware AppDefense component. The AppDefense components consists of glxgi.sys kernel mode driver and gisvc.exe user mode service. |
| **Toolbox** | Perfmon | Driver for WMI performance logging. |

The latest version of the VMware Tools component values can be found here, [link](https://docs.vmware.com/en/VMware-Tools/index.html)

## Extract the VMware ISO for drivers

Sometimes is handy to extract the VMware ISO to get the VMXnet3 and PVSCSI drivers.

- Mount the ISO
- setup64.exe /A /P C:\\Folder to extract

## PowerCLI

To identify and upgrade the VMware Tools versions PowerCLI is your friend. First install the PowerCLI module, [link](http://localhost/2019/07/16/powercli-installation-updating-and-troubleshooting-tips/). After the module is installed, connect to the vCenter Server.

```powershell

$vcsa = "vcsa03.lab.local"

Import-Module VMware.PowerCLI  
Connect-VIServer -Server $vcsa  
```

**Identify VMware Tools versions**

To get the VMware Tools versions of the running VMs use the following PowerCLI command:

```powershellGet-VM | Get-VMguest | Where {$\_.State -eq ‘Running’} | Select VmName, ToolsVersion```

- Get all the running VMs that don’t have VMware Tools version 10.3.10 installed:

```powershellGet-VM | Get-VMguest | Where-Object {$\_.State -eq ‘Running’ -and $\_.ToolsVersion -notlike ‘10.3.10’} | Select VmName, ToolsVersion```

- Get all the running VMs that have an outdated version of VMware Tools:

```powershell  
Get-VM | Get-VMguest | where-object {$\_.State -eq ‘Running’ -and $\_.ExtensionData.ToolsversionStatus -eq ‘GuestToolsNeedUpgrade’} | Select VmName  
```

**Update VMware Tools**

Once you have an overview of all the VMware Tools versions that are outdated is easy to upgrade them to the latest version. In this example, the -NoReboot option is used so the OS will not be rebooted. Make sure when using -NoReboot option that the reboot will be planned in a maintenance window. This stops for example installing Windows Updates because there is a pending reboot action that needs to be performed first.

First export all the VMs to a CSV file that will be saved under c:\\temp\\vms.csv

```powershell  
Get-VM | Get-VMguest | where-object {$\_.State -eq ‘Running’ -and $\_.ExtensionData.ToolsversionStatus -eq ‘GuestToolsNeedUpgrade’} | Select VmName | export-csv c:\\temp\\vms.csv -NoTypeInformation  
```

Verify the CSV file and make sure only the VMs are listed that need to be upgraded. After that import the CSV and update the VMware Tools using the following commands:

```powershell  
$vms = Import-Csv c:\\temp\\vms.csv  
$vms | % { get-vm -name $\_.VmName | Update-Tools -NoReboot}  
```
