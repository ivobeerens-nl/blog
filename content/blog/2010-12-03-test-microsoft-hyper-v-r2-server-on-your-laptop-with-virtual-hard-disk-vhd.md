---
author: Ivo Beerens
categories:
- Hyper-V
- microsoft
date: "2010-12-03T11:29:40Z"
guid: http://www.ivobeerens.nl/?p=745
id: 745
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hyper-v
- microsoft
title: Test Microsoft Hyper-V R2 server on your laptop with Virtual Hard Disk (VHD)
url: /2010/12/03/test-microsoft-hyper-v-r2-server-on-your-laptop-with-virtual-hard-disk-vhd/
---

<font color="#000000">When you want to test some Microsoft Hyper-V R2 stuff it’s handy to do that on your laptop. I test a lot stuff on my laptop equipped with Microsoft Windows 7, 8GB RAM and VMware Workstation. Installing Microsoft Hyper-V R2 for example in VMware Workstation is possible, but it is not possible to start any Virtual Machines (VMs). Microsoft Hyper-V requires a processor with Intel-VT or AMD-V with the No-Execute (NX) feature. In VMware Workstation the virtual CPU has no VT.</font>

<font color="#000000">So how could I test Microsoft Hyper-V R2 and start VMs on my laptop? The solution is by using **Virtual Hard Disks (VHDs).** </font>

<font color="#000000">Microsoft Windows 7 and Microsoft Windows 2008 R2 provides native support for Virtual Hard Disks (VHD). With Windows 7 (Enterprise and Ultimate editions) and Windows 2008 R2 (All versions except Windows 2008 R2 Foundation) you can create, configure and boot from VHD.</font>

<font color="#000000">Here’s how to create, install and boot the VHD equipped with Microsoft WIndows 2008 R2 (so you could install the Microsoft Hyper-V role) in Microsoft Windows 7.</font>

**<font color="#000000">Step 1 Create a VHD using Disk Management</font>**

- <font color="#000000">In Microsoft Windows 7 open Disk Management (diskmgmt.msc) </font>
- <font color="#000000">From the Action menu choose ‘Create VHD’ </font>
- <font color="#000000">Select the location to store the VHD disk file and choose a VHD size. For the best performance use a fixed size. </font>

[<font color="#000000">![2010-12-02 11h14_54](http://localhost/wp-content/uploads/2010/12/2010-12-02-11h14_54_thumb.jpg "2010-12-02 11h14_54")</font>](http://localhost/wp-content/uploads/2010/12/2010-12-02-11h14_54.jpg)

- <font color="#000000">Initialize the VHD disk and assign a drive letter, a name and format the disk. In this example the VHD has drive letter G. </font>

[<font color="#000000">![2010-12-02 11h13_30](http://localhost/wp-content/uploads/2010/12/2010-12-02-11h13_30_thumb.jpg "2010-12-02 11h13_30")</font>](http://localhost/wp-content/uploads/2010/12/2010-12-02-11h13_30.jpg)

**<font color="#000000">Step 2 Transfer the image to the VHD</font>**

- <font color="#000000">Mount the ISO image of Windows 2008 R2 (available for <span lang="EN-US" style="font-family: "Arial","sans-serif"; font-size: 10pt; mso-ansi-language: en-us; mso-fareast-font-family: simsun; mso-bidi-font-family: 'Times New Roman'; mso-fareast-language: en-us; mso-font-kerning: 12.0pt; mso-bidi-language: ar-sa">MSDN and TechNet subscribers)</span>. The ISO contains multiple images of different versions of Windows 2008 R2 and Windows 7. Here’s a list with the corresponding index number and the WIM images (found in the Install.wim). </font>

| **<span lang="EN-US" style="font-size: 9pt"><font color="#000000" face="Arial">Index </font></span>** | **<span lang="EN-US" style="font-size: 9pt"><font color="#000000" face="Arial">Operating System Edition </font></span>** |
|---|---|
| <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">1 </font></font></span> | <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">Windows 7 Enterprise </font></font></span> |
| <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">4 </font></font></span> | <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">Windows 7 Ultimate </font></font></span> |
| <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">1 </font></font></span> | <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">Windows Server 2008 R2 Standard (Full Installation) </font></font></span> |
| <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">2 </font></font></span> | <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">Windows Server 2008 R2 Standard (Server Core Installation) </font></font></span> |
| <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">3 </font></font></span> | <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">Windows Server 2008 R2 Enterprise (Full Installation) </font></font></span> |
| <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">4 </font></font></span> | <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">Windows Server 2008 R2 Enterprise (Server Core Installation) </font></font></span> |
| <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">5 </font></font></span> | <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">Windows Server 2008 R2 Datacenter (Full Installation) </font></font></span> |
| <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">6 </font></font></span> | <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">Windows Server 2008 R2 Datacenter (Server Core Installation) </font></font></span> |
| <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">7 </font></font></span> | <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">Windows Web Server 2008 R2 (Full Installation) </font></font></span> |
| <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">8 </font></font></span> | <span lang="EN-US"><font size="2"><font color="#000000" face="Arial">Windows Web Server 2008 R2 (Server Core Installation) </font></font></span> |

<font color="#000000"></font>

<font color="#000000">Now we need to apply he WIM image to the VHD partition by using the ‘**Install-WindowsImage.ps1’** PowerShell script. This Powershell script does the following:</font>

> <span id="ctl00_ctl00_Content_TabContentPanel_Content_wikiSourceLabel"><font color="#000000">The Install-WindowsImage PowerShell script uses the wimgapi.dll in Windows 7 or Windows Server 2008 R2 to apply a Windows image in a .wim file to a specified location. The script can be used to apply a Windows 7 or Windows Server 2008 R2 .wim image to a Virtual Hard Disk (VHD) used for native VHD boot or to boot in a Hyper-V virtual machine.</font></span>

- <font color="#000000">Download the ‘Install-WindowsImage’ PowerShell script </font>[<font color="#000000">here</font>](http://code.msdn.microsoft.com/InstallWindowsImage)<font color="#000000">. </font>
- <font color="#000000">Open PowerShell and and use the following syntax to apply the image to the VHD.: </font>
- <font color="#000000">.\\Install-WindowsImage.ps1 –WIM <CDROMDriveLetter\\sources\\install.wim> -Apply -Index WIMimagenumber –Destination <VHD Drive></font>

> <font color="#000000">Example: </font>
> 
> <font color="#000000">.\\Install-WindowsImage.ps1 -WIM Z:\\sources\\install.wim -Apply -Index 3 -Destination G: </font>

- <font color="#000000">The WIM image is now applying to the VHD. This can take up to 15 minutes. </font>

<font color="#000000"></font>

**<font color="#000000">Step 3 Prepare the VHD image for native boot</font>**

- <font color="#000000">Open the command prompt (**RUN as Administrator**) </font>
- <font color="#000000">Create a new Boot Configuration Data (BCD) entry for native boot using the following syntax: </font>

> <font color="#000000">g:\\Windows\\System32\\bcdboot g:\\Windows </font>

- <font color="#000000">Using the command bcdedit command you can see the new boot entry pointing to the VHD image </font>

[<font color="#000000">![2010-12-02 12h50_02](http://localhost/wp-content/uploads/2010/12/2010-12-02-12h50_02_thumb.jpg "2010-12-02 12h50_02")</font>](http://localhost/wp-content/uploads/2010/12/2010-12-02-12h50_02.jpg)

- <font color="#000000">To change the default boot options use the **bcdedit –v** command to list the associated GUID numbers. Use the **bcdedit / default {GUID}** command to set the default boot config. A easier option is to use the **MSCONFIG** command to set the default boot entry and the timeout. </font>

 [<font color="#000000">![image](http://localhost/wp-content/uploads/2010/12/image_thumb.png "image")</font>](http://localhost/wp-content/uploads/2010/12/image.png)<font color="#000000"> </font>

<font color="#000000">When restarting Microsoft Windows 7, there is an extra option for booting the Windows 2008 R2 server OS and your able to install the Microsoft Hyper-V R2 role. </font>

<font color="#000000">More information can be found in the Microsoft Windows 2008 R2 Getting Started with Virtual Hard Disks document.</font>

<font color="#000000"></font>
