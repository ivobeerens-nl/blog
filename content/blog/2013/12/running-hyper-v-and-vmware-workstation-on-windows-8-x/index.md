---
title: "Running Hyper-V and VMware Workstation on Windows 8.x"
date: "2013-12-16T19:40:29.000Z"
categories: 
  - "hyper-v"
  - "VMware"
  - "workstation"
tags: 
  - "hyper-v-2"
  - "VMware"
  - "workstation"
author: Ivo Beerens
---

<table border="0" width="400" cellspacing="0" cellpadding="2"><tbody><tr><td valign="top" width="200"><a href="images/image2.png"><img style="background-image: none; padding-top: 0px; padding-left: 0px; display: inline; padding-right: 0px; border: 0px;" title="image" src="images/image_thumb2.png" alt="image" width="237" height="213" border="0"></a></td><td valign="top" width="200"><a href="https://www.ivobeerens.nl/wp-content/uploads/2013/12/image3.png"><img style="background-image: none; padding-top: 0px; padding-left: 0px; display: inline; padding-right: 0px; border: 0px;" title="image" src="images/image_thumb3.png" alt="image" width="244" height="184" border="0"></a></td></tr><tr><td valign="top" width="200">1. VHD disk</td><td valign="top" width="200">2. Convert options in Hyper-V</td></tr></tbody></table>

That’s why I use Hyper-V on my laptop sometimes. When trying to start VMware Workstation the following error appears:

> VMware Workstation and Hyper-V are not compatible. Remove the Hyper-V role from the system before running VMware Workstation.

[![image](images/image_thumb4.png "image")](images/image4.png)

This is because the Hyper-V role is installed and this conflicts with VMware Workstation. To disable Hyper-V from starting the following command can be used:

bcdedit /set hypervisorlaunchtype off

A reboot of of the Windows OS is necessary.

To enable the Hyper-V role again use the following command:

bcdedit /set hypervisorlaunchtype auto

A reboot of of the Windows OS is necessary.



