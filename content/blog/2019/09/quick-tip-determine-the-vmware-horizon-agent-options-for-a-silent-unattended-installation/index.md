---
title: "Quick tip: Determine the VMware Horizon Agent options for a silent/unattended installation"
date: "2019-09-30T10:35:37.000Z"
author: Ivo Beerens
---

A quick way to determine what options are available for the Horizon Agent that can be used is to install the Horizon Agent and manually select/deselect the options. After the installation and reboot open Regedit an browse to the following location:

\[code language="text"\]HKEY\_LOCAL\_MACHINE\\Software\\VMware, Inc.\\Installer\\Features\_HorizonAgent\[/code\]

[![](images/Latest-300x162.jpg)](images/Latest.jpg)

Al the options/features are listed and have a value of:

- **Local** = Installed/enabled
- **Absent** = Not Installed/disabled

These options can be used for silent installing the VMware Horizon Agent. Here is an example that install the Horizon Agent:

\[code language="text"\] VMware-Horizon-Agent-x86\_64-7.10.0-14590940.exe  /s /v"/qn VDM\_VC\_MANAGED\_AGENT=1 VDM\_FLASH\_URL\_REDIRECTION=1 RDP\_CHOICE=1 INSTALL\_VDISPLAY\_DRIVER=1 ADDLOCAL=BlastUDP,Core,HelpDesk,NGVC,PerfTracker,ClientDriveRedirection,RTAV,RDP,ThinPrint,TSMMR,USB,V4V,VMWMediaProviderProxy,VmwVaudio,VmwVdisplay,VmwVidd REBOOT=Reallysuppress" \[/code\]

In this example the following MSI properties are installed:

- RDP is enabled
- The agent is installed is a vCenter Managed desktop
- Flash URL redirection is enabled
- Installs the WDDM display driver

For the VMware Horizon Agent options refer to the following [link](https://docs.VMware.com/en/VMware-Horizon-7/7.10/horizon-published-desktops-applications/GUID-3096DA8B-034B-435B-877E-5D2B18672A95.html?hWord=N4IghgNiBcIM4EsIFMB2AXABA1d2QjHQQHtUQBfIA).



