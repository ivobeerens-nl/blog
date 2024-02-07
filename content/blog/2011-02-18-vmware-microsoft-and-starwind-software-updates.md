---
author: Ivo Beerens
categories:
- ESX
- ESXi
- microsoft
- Startwind
- VMware
- vSphere
date: "2011-02-18T14:36:06Z"
guid: http://www.ivobeerens.nl/?p=777
id: 777
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- microsoft
- starwind
- vpshere
title: VMware, Microsoft and Starwind software updates
url: /2011/02/18/vmware-microsoft-and-starwind-software-updates/
---

<font color="#000000">Last weeks a lots of software updates and new releases are published. Here’s an overview of some of them:</font>

## <font color="#0000ff">VMware</font>

#### <font color="#000000">**VMware vSphere 4.1 Update 1**</font>

<font color="#000000">A new update for vSphere 4.1 is released. Here are the ESX(i) and vCenter improvements:</font>

<font color="#000000">*VMware ESX(i) 4.1 Update 1 improvements*:</font>

- <font color="#000000">Enablement of Trusted Execution Technology (TXT) — ESXi 4.1 Update 1 can be configured to boot with Intel Trusted Execution Technology (TXT). This boot option can protect ESXi in some cases where system binaries are corrupted or have been tampered with. TXT is currently available on Intel Xeon processor 5600 series servers. For more information, see KB 1033811. </font>
- <font color="#000000">Improvement in scalability — ESXi 4.1 Update 1 supports up to 160 logical processors. </font>
- <font color="#000000">Support for additional guest operating systems — ESXi 4.1 Update 1 provides support for RHEL 6, RHEL 5.6, SLES 11 SP1 for VMware, Ubuntu 10.10, and Solaris 10 Update 9 guest operating systems. For a complete list of guest operating systems supported in this release, see the VMware Compatibility Guide. </font>
- <font color="#000000">Inclusion of additional drivers — ESXi 4.1 Update 1 includes the 3ware SCSI 2.26.08.036vm40 and Neterion vxge 2.0.28.21239-p3.0.1.2 drivers. For earlier releases, these drivers are only available as separate downloads </font>

<font color="#000000">The release notes can be found </font>[<font color="#000000">here</font>](http://www.vmware.com/support/vsphere4/doc/vsp_esxi41_u1_rel_notes.html#resolvedissues)<font color="#000000">.</font>

<font color="#000000">*VMware vCenter Server 4.1 Update 1 improvements*:</font>

- <font color="#000000">Additional Guest Operating System Customization Support: vCenter Server now supports customization of the following guest operating systems: </font>
    - <font color="#000000">Windows 7 SP1 (x32 and x64) </font>
    - <font color="#000000">Windows Server 2008 R2 SP1 (x32 and x64) </font>
    - <font color="#000000">RHEL 6.0 (x32 and x64) </font>
    - <font color="#000000">RHEL5.5 (x32 and x64) </font>
- <font color="#000000">Additional vCenter Server Database Support**:** vCenter Server now supports the following databases: </font>
    - <font color="#000000">Microsoft SQL Server 2008 R2 </font>
    - <font color="#000000">Microsoft SQL Server 2005 SP3 </font>
    - <font color="#000000">Oracle 11g Standard/Enterprise Release 2, 11.2.0.1.0 or later, (x32 and x64) </font>
    - <font color="#000000">IBM DB2 9.7.2 Express C (x32 and x64) </font>
    - <font color="#000000">IBM DB2 9.7.2 Enterprise (x32 and x64)   
        For more information about using IBM DB2 – 9.7.2 database with vCenter Server 4.1 Update 1, see </font>[<font color="#000000">KB 1033201</font>](http://kb.vmware.com/kb/1033201)<font color="#000000">. </font>

<font color="#000000">The release notes can be found </font>[<font color="#000000">here.</font>](http://www.vmware.com/support/vsphere4/doc/vsp_vc41_u1_rel_notes.html#resolvedissues)

<font color="#000000">vSphere 4.1 Update 1 can be downloaded </font>[<font color="#000000">here</font>](http://downloads.vmware.com/d/info/datacenter_downloads/vmware_vsphere_4/4_0)<font color="#000000">.</font>

#### **<font color="#000000">VMware Data Recovery (vDR)</font>**

<font color="#000000">There is NO new version of vDR but it is now included in the standard edition of vSphere since vSphere 4.1 Update 1. You can compare the vSphere versions </font>[<font color="#000000">here</font>](http://www.vmware.com/products/vsphere/buy/editions_comparison.html)<font color="#000000">. For people who have who already bought vSphere standard and have a current subscription are able to download the vDR.</font>

#### <font color="#000000">**VMware ESX 3.0.3 patches** </font>

<font color="#000000">A new VMware ESX 3.0.3 patches are released . More information on these patches can be found in the following links: </font>

- [<font color="#000000">http://kb.vmware.com/kb/<wbr></wbr>1031234</font>](http://kb.vmware.com/kb/1031234)<font color="#000000"> </font>
- [<font color="#000000">http://kb.vmware.com/kb/<wbr></wbr>1031235</font>](http://kb.vmware.com/kb/1031235)<font color="#000000"> </font>
- [<font color="#000000">http://kb.vmware.com/kb/<wbr></wbr>1031238</font>](http://kb.vmware.com/kb/1031238)<font color="#000000"> </font>

<font color="#000000">The ESX 3.0.3 patches can be downloaded </font>[<font color="#000000">here</font>](http://www.vmware.com/patch/download/)<font color="#000000">. </font>

#### <font color="#000000">**VMware vCloud Director 1.0.1**</font>

<font color="#000000">New features are support for vSphere 4.1 Update 1, complies with Internationalization I18N Level 1 and IP Translation for Organization Networks support. The release notes can be found </font>[<font color="#000000">here</font>](http://www.vmware.com/support/vcd/doc/rel_notes_vcloud_director_101.html)<font color="#000000">.</font>

#### <font color="#000000">**vCenter Server Heartbeat 6.3 Update 1**</font>

<font color="#000000">The following enhancements (**Note:** The features available depend on the version of vCenter Server installed) are available in this release:</font>

- <font color="#000000">Enhanced passive server management capabilities — A new deployment option allows the passive server to be managed and monitored remotely, this includes receiving file level antivirus updates. This option is only available for: </font>
    - <font color="#000000">vCenter 4.0 U1 and its updates, 4.1 and its updates </font>
    - <font color="#000000">Remote SQL Server 2005, 2008 onl </font>

<font color="#000000">Please refer to install documentation for detailed requirements and install procedure specifically around DNS and changes required to Active Directory during installation. </font>

- <font color="#000000">Secure Client Server Communications — vCenter Server Heartbeat now provides secure client server communications with SSL Encryption using a 2048-bit key. </font>
- <font color="#000000">Support for View Composer — This release of VMware vCenter Server Heartbeat now provides support for View Composer v2.5 </font>

<font color="#000000">The vCenter Server Heartbeat 6.3 Update 1 release notes can be found </font>[<font color="#000000">here</font>](http://www.vmware.com/support/heartbeat/doc/vcenter-server-heartbeat-63-u1-release-notes.html)<font color="#000000"> and downloaded </font>[<font color="#000000">here</font>](http://downloads.vmware.com/d/info/datacenter_downloads/vmware_vsphere_4/4_0)<font color="#000000">.</font>

#### <font color="#000000" style="font-weight: bold">VMware vCenter Site Recovery Manager 4.1.1 </font>

<font color="#000000">VMware SRM 4.1.1 in a maintenance release. It has bugfixes and supports VMware vSphere 4.1 Update 1. Before installing VMware SRM 4.1.1 you need to update the vCenter server to 4.1 Update 1. The release notes can be found </font>[<font color="#000000">here</font>](http://www.vmware.com/support/srm/srm_releasenotes_4_1_1.html)<font color="#000000"> an be downloaded </font>[<font color="#000000">here</font>](http://downloads.vmware.com/d/info/datacenter_downloads/vmware_vcenter_site_recovery_manager/4_0#product_downloads)<font color="#000000">.</font><font color="#000000"> </font>

## <font color="#0000ff">Microsoft</font>

#### <font color="#000000" style="font-weight: bold">System Center Virtual Machine Manager 2008 R2 (SCVMM) </font>

<font color="#000000">Microsoft has published a </font>[<font color="#000000">KB</font>](http://support.microsoft.com/default.aspx?scid=kb;EN-US;2397711)<font color="#000000"> with the recommend hotfixes when performing P2V conversions by using SCVMM R2. </font>

#### <font color="#000000" style="font-weight: bold">Windows Server 2008 R2 / Windows 7 SP1 </font>

<font color="#000000">On Technet and MSDN SP1 for Windows 2008 R2 and Windows 7 is released. SP1 has a lot of patches and bug fixes. Two new features are memory compression (Hyper-V) and Remote FX (Remote Desktop Services).</font>

## <font color="#0000ff">Starwind</font>

#### <font color="#000000" style="font-weight: bold">Starwind iSCSI SAN 5.6</font>

<font color="#000000">A new version of the Starwind iSCSI SAN 5.6 is released. The Starwind iSCSI SAN software converts a Windows bases server into a fail-safe, highly available iSCSI SAN. This release has the following improvements:</font>

<font color="#000000"></font>

- <font color="#000000">Event Log – Improve your storage management and tracking of system state with new event viewer   
    </font>
- <font color="#000000">Event notifications – Be aware of every single event by e-mail, records to Windows Event Log, records to text files   
    </font>
- <font color="#000000">Experimental version of inline block level Deduplication plugin   
    </font>
- <font color="#000000">Management Console multilevel improvements</font>

<font color="#000000">Starwind offers a free NFR license valid for 6 months for MCP, MVP and VCP certified people. Request the NFR </font>[<font color="#000000">here</font>](http://www.starwindsoftware.com/nfr-request)<font color="#000000">. The installation and configuration is very simple. Within a couple of minutes you have an working iSCSI SAN. it support Microsoft Hyper-V R2 Live migration (SCP-3 persistent reservations) and VMware vSphere clustering with DRS, HA and VMotion.</font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

[![image](http://localhost/wp-content/uploads/2011/02/image_thumb.png "image")](http://localhost/wp-content/uploads/2011/02/image.png)
