---
author: Ivo Beerens
categories:
- VMware
date: "2022-04-14T13:32:54Z"
guid: https://www.ivobeerens.nl/?p=8302
id: 8302
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- vmware tools
title: An unattended installation of VMware Tools 12 generates a 2711 error
url: /2022/04/14/vmware-tools-error-2711/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

For a new Windows 10 image build, I used the latest supported VMware Tools In this case that was VMware Tools 12.0.0. VMware Tools is deployed using an unattended installation such as:

```powershell  
e:\\setup64.exe /S /v "/qb REBOOT=R ADDLOCAL=All REMOVE=AppDefense,Hgfs,CBHelper,VmwTimeProvider,VSS,NetworkIntrospection,FileIntrospection" /l c:\\windows\\temp\\vmware\_tools\_install.log  
```

During the installation of VMware Tools, the following error occurred: “The installer has encountered an unexpected error installing this package. This may indicate a problem with this package. The error code is 2711.”

[![](http://localhost/wp-content/uploads/2022/04/3-300x118.jpg)](http://localhost/wp-content/uploads/2022/04/3.jpg)

After comparing the syntax of the components and could not find any clue ([link](https://docs.vmware.com/en/VMware-Tools/12.0.0/com.vmware.vsphere.vmwaretools.doc/GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC.html)).

| Feature Name | Description |
|---|---|
| CBHelper | Helper to install of Carbon black Sensor on a virtual machine. |
| Perfmon | Utility for WMI performance logging. Enables performance monitoring between the Guest SDK and the WMI environment. |
| VmwTimeProvider | Time provider for VMware virtual precision clock device. |
| AppDefense | The VMware AppDefense component performs Application Security Monitoring. VMware Appdefense consists of <span class="ph filepath">glxgi.sys</span>, <span class="ph filepath">giappdef.sys</span> kernel mode drivers and <span class="ph filepath">gisvc.exe</span> user mode service. |
| FileIntrospection | The NSX File Introspection driver, <span class="ph filepath">vsepflt.sys</span> is the first of the two guest introspection drivers. You can install it separately, without installing the NSX Network Introspection driver. <div class="note note note_note" id="GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC__NOTE_6E565793-A156-45FB-AD02-4C67F672F318"><span class="note__title">Note:</span>This component is dependent on the VMCI driver.</div> |
| NetworkIntrospection | The NSX Network Introspection driver, <span class="ph filepath">vnetflt.sys</span> is the second of the two guest introspection drivers. <div class="note note note_note" id="GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC__NOTE_2E104931-62AE-41FC-8FFA-7C98BAFAC234"><span class="note__title">Note:</span>This component is dependent on the VMCI driver.</div>VMware Tools 10.2.5 supports vnetWFP driver for Windows 7 and later. |
| ServiceDiscovery | The Service Discovery component enables the discovery of various services running inside a virtual machine. <div class="note note note_note" id="GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC__NOTE_08C188FB-523C-4A0B-B4B7-DF07FD4A48EC"><span class="note__title">Note:</span>This user-mode component is dependent on the VMCI driver.</div> |
| DeviceHelper | The VMware Device Helper component helps to perform a device check and swap in your virtual machine. <div class="note note note_note" id="GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC__NOTE_A72636F7-67E1-41E6-80C8-B2D9D1EE187C"><span class="note__title">Note:</span>This user-mode component is dependent on the VMCI driver.</div> |
| Hgfs | Hgfs is a VMware shared folders driver that allows files to be shared between your virtual machine and the host computer. <div class="p" id="GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC__P_BC7E88D1-92AC-47B1-AFD1-AB1768D5A91B">You can use this driver, if you plan to use this virtual machine with VMware Workstation, Player, or Fusion.  <div class="note note note_note" id="GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC__NOTE_67AEBF00-4367-42DD-87E0-170B7553D471"><span class="note__title">Note:</span>  - If you exclude this feature, you cannot share a folder between your virtual machine and the host system. - This component is dependent on the VMCI driver.  </div></div> |
| SVGA | The VMware SVGA driver enhances the performance of your virtual video card. <div class="note note note_note" id="GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC__NOTE_891678E5-CBE9-4B6A-9119-C55792911BAD"><span class="note__title">Note:</span>If you exclude this feature, it limits the display capabilities of your virtual machine.</div> |
| VMXNet | The VMware VMXNet networking driver enhances the performance of your virtual network card. |
| VMXNet3 | The VMware VMXNet3 networking driver enahnces the performance of your virtual network card (ndis5/ndis6). This is the Next-generation VMware VMXnet networking driver for virtual machines that use virtual hardware version 7 and higher. For more information, see the VMware Knowledge Base article [KB 1001805](https://kb.vmware.com/s/article/1001805).  VMXNET3 adds several new features, such as multiqueue support (also known as ‘Receive Side Scaling’ in Windows), IPv6 offloads, and MSI/MSI-X interrupt delivery.  VMXNET 3 is not related to VMXNET or VMXNET 2.  Receive Side Scaling is enabled by default.  VMware Tools 10.3.0 adds receive data ring support for Windows VMXNET3 driver.  Virtual hardware version 7 corresponds to ESX/ESXi 4.x compatibility. |
| PVSCSI | The VMware Paravirtual SCSI adapters enhances the performance of your paravirtual SCSI devices. |
| EFIFW | The EFIFW driver is used for EFI Firmware update. |
| MemCtl | The Memory Control Driver provides enahnced memory management of the virtual machine. <div class="p" id="GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC__P_5CE50666-44B9-4E26-839A-AE11EECD83EB">You can use this driver, if you plan to use a virtual machine in the vSphere environment.  <div class="note note note_note" id="GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC__NOTE_145DE29C-12FA-4F6E-9B7F-C2E6D5BD7B3B"><span class="note__title">Note:</span>If you exclude this feature, it hinders the memory management capabilities of the virtual machine running in a vSphere environment.</div></div> |
| Mouse | The VMware PS2 Mouse driver enhances the performance of your virtual PS2 mouse. <div class="note note note_note" id="GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC__NOTE_FA3B7472-AB6A-4FBB-AAB1-5DD78C399BBA"><span class="note__title">Note:</span>If you exclude this feature, the mouse performance of your virtual machine will decrease.</div> |
| MouesUsb | The VMware USB Mouse Driver enhances performance of your USB mouse. |
| Audio | The Audio driver provides audio for your virtual sound card. <div class="note note note_note" id="GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC__NOTE_65E29D2D-7895-4051-830A-7D97DA492BDB"><span class="note__title">Note:</span>This Audio driver is for 64-bit Windows Vista and later operating systems.</div> |
| VSS | The VSS driver is used for creating automatic backups. This driver is used, if the guest operating system is Windows Vista, Windows Server 2003, or other newer operating systems. Linux and older Windows operating systems use the Filesystem Sync driver. |
| BootCamp | The BootCamp driver provides Mac BootCamp support. |

So I decided to install VMware Tools 12 manually and search in the Windows registry for the components:

[![](http://localhost/wp-content/uploads/2022/04/4-238x300.jpg)](http://localhost/wp-content/uploads/2022/04/4.jpg)

As you can see, the AppDefense component doesn’t exist anymore in VMware Tools 12. Removing the AppDefense component from the unattended VMware Tools installation command fixed the problem.

```powershell  
e:\\setup64.exe /S /v "/qb REBOOT=R ADDLOCAL=All REMOVE=Hgfs,CBHelper,VmwTimeProvider,VSS,NetworkIntrospection,FileIntrospection" /l c:\\windows\\temp\\vmware\_tools\_install.log  
```

I filled in a feedback form on the VMware Tools 12 documentation page to change to remove the AppDefense component.
