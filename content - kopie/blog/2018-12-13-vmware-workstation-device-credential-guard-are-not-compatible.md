---
author: Ivo Beerens
categories:
- workstation
date: "2018-12-13T08:36:21Z"
guid: https://www.ivobeerens.nl/?p=6501
id: 6501
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- VMware Workstation
title: VMware Workstation Device/Credential Guard are not compatible
url: /2018/12/13/vmware-workstation-device-credential-guard-are-not-compatible/
---

When using VMware Workstation 15 Pro with on Windows 10 with the Hyper-V role enabled I’ve got the following error when trying to install or start Windows 10 in VMware Workstation:

> VMware Workstation and Device/Credential Guard are not compatible. VMware Workstation can be run after disabling Device/Credential Guard. Please visit http://www.vmware.com/go/turnoff\_CG\_DG for more details.

[![](http://localhost/wp-content/uploads/2018/12/workstation-300x124.png)](http://localhost/wp-content/uploads/2018/12/workstation.png)

In 2013 I did a post about using VMware Workstation and Hyper-V together on Windows 8, [link](http://localhost/2013/12/16/running-hyper-v-and-vmware-workstation-on-windows-8-x/). The bottom line that the Hyper-V role conflicts with VMware Workstation. It looks like this is still the case. The same solution can be used to disable the Hyper-V role in Windows 10.

To disable Hyper-V from starting the following command can be used:

<span style="font-family: 'Courier New';">bcdedit /set hypervisorlaunchtype off</span>

A reboot of Windows 10 is necessary. After the reboot I was able to boot the Windows 10 VM.

[![](http://localhost/wp-content/uploads/2018/12/Windows10-300x144.png)](http://localhost/wp-content/uploads/2018/12/Windows10.png)

To enable the Hyper-V role again use the following command:

<span style="font-family: 'Courier New';">bcdedit /set hypervisorlaunchtype auto</span>

A reboot of of the Windows 10 is necessary.

VMware/Microsoft has a KB article how to disable Windows Defender Credential Guard, [link ](https://kb.vmware.com/s/article/2146361)and [link](https://docs.microsoft.com/en-us/windows/security/identity-protection/credential-guard/credential-guard-manage). I did not try this because the solution in this worked for me.
