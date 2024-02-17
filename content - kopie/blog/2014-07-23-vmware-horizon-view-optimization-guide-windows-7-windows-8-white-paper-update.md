---
author: Ivo Beerens
categories:
- VDI
- VMware Horizon VIew
- VMware View
date: "2014-07-23T14:10:06Z"
guid: http://www.ivobeerens.nl/?p=2899
id: 2899
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Horizon View
- VDI
- VMware
- Windows 7
- windows 8
title: VMware Horizon View Optimization Guide for Windows 7 and Windows 8 white paper
  update
url: /2014/07/23/vmware-horizon-view-optimization-guide-windows-7-windows-8-white-paper-update/
---

VMware released an updated version of the “VMware Horizon with View Optimization Guide for Windows 7 and Windows 8” whitepaper. This white paper discuss the necessary information for optimizing a Windows 7 or Windows 8 virtual desktop image for VMware Horizon View using the Microsoft Deployment Toolkit (MDT) or use a script-based approach.

The updated (July 15, 2014) “VMware Horizon with View Optimization Guide for Windows 7 and Windows 8” whitepaper can be found here. [Link](https://www.vmware.com/resources/techresources/10157?utm_content=buffer99b4d&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer)

**Changelog scripts:**

**Removed on 03 June 2014**  
*The following code was removed to fix issues with IE10, IE11, and Adobe Acrobat:  
rem reg ADD “HKLM\\System\\CurrentControlSet\\Control\\Session Manager\\Memory  
Management” /v MoveImages /t REG\_DWORD /d 0x0 /f*

**Removed on 11 February 2014** *Rem Remove recycling bin*  
*reg ADD “HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\  
policies\\Explorer” /v NoRecycleFiles /t REG\_DWORD /d 0x1 /f*

### **Updated version of the VMware OS Optimization Tool**

The VMware Labs Flings has an updated version of the “VMware OS Optimalization Tool”. The VMware OS Optimization Tool helps optimize Windows 7/8/2008/2012 systems for use with VMware Horizon View. New enhancements are:

- Updated templates for Windows 7/8 – based on VMware’s OS Optimization Guide
- New templates for Windows 2008/2012 RDSH servers for use as a desktop
- Single portal EXE design for ease of deployment and distribution
- Combination of Remote and Local tools into one tool
- Better template management, with built in and user-definable templates
- Results report export feature.

The VMware OS Optimization Tool can be found here, [link](https://labs.vmware.com/flings/vmware-os-optimization-tool)
