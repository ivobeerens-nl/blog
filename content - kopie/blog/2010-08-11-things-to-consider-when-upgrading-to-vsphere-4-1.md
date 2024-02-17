---
author: Ivo Beerens
categories:
- upgrade
- VMware
date: "2010-08-11T11:10:49Z"
guid: http://www.ivobeerens.nl/?p=566
id: 566
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- scripted
- vCenter
- VMware
- vSphere
- vsphere 4.1
title: Things to consider when upgrading to vSphere 4.1
url: /2010/08/11/things-to-consider-when-upgrading-to-vsphere-4-1/
---

<font color="#000000"> </font>

<font color="#000000">The new vSphere 4.1 release offers a lot of new cool features and enhancements. </font>[<font color="#000000">Here’s a list What’s New in vSphere 4.1.</font>](http://www.vmware.com/support/vsphere4/doc/vsp_41_new_feat.html)<font color="#000000"> When upgrading to vSphere 4.1 there are a couple of things to think about before starting: </font>

- <font color="#000000">Make sure your systems and components are supported, check the </font>[<font color="#000000">Hardware Compatibility Guide</font>](http://www.vmware.com/resources/compatibility/search.php)<font color="#000000">. </font>
- <font color="#000000">Verify that other products are compatible with vSphere 4.1. For example VMware View 4 is not supported on vSphere 4.1. VMware View composer does not support 64-bit operating systems. </font>
- <font color="#000000">vCenter 4.1 server requires a 64-bit OS. 32-bit Operating Systems are not supported anymore for vCenter 4.1 server. </font>
- <font color="#000000">vSphere 4.1 and its subsequent update and patch releases are the last releases to include both ESX and ESXi hypervisor architectures. Future major releases of VMware vSphere will include only the VMware ESXi architecture. For this reason, **VMware recommends that deployments of vSphere 4.x utilize the ESXi hypervisor architecture**. When migrate to ESXi all the script and programs (such as hardware monitoring agents and backup agents), that uses the Service Console needs to replaced. More information can be the following links </font>[<font color="#000000">ESX4.1 is the last ESX what do i do now</font>](http://blogs.vmware.com/vsphere/2010/07/esx-41-is-the-last-esx-what-do-i-do-now.html)<font color="#000000"> and in the </font>[<font color="#000000">ESXi41 Migration Guide</font>](http://www.vmware.com/files/pdf/techpaper/VMW-ESXi41-Migration-Guide.pdf)<font color="#000000">. </font>
- <font color="#000000">vSphere 4.1 support scripted installation for ESXi. **You cannot use scripted installation to install ESXi to a USB device!** Here are some good links for scripted ESXi 4.1 installations: **Kenneth van Ditmarsch**, </font>[<font color="#000000">Setting up vSphere ESXi 4.1 scripted installation</font>](http://virtualkenneth.com/2010/07/21/setting-up-vsphere-esxi-4-1-scripted-installation/)<font color="#000000">, **Kendrick Coleman**, </font>[<font color="#000000">ESX 4.1 Kickstart install</font>](http://kendrickcoleman.com/index.php?/Tech-Blog/esxi-41-kickstart-install-wip.html)<font color="#000000">, **Billhill**, </font>[<font color="#000000">Setting up vSphere ESX 4.1 scripted installation from Ubuntu</font>](http://communities.vmware.com/blogs/vmwareinsmb/2010/07/13/esxi-41-scripted-installation-via-pxe-and-kickstart)<font color="#000000"> and </font>[<font color="#000000">Deploy ESXi 4.1 using Scripted install feature</font>](<http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1022263 >)<font color="#000000">. </font>
- <font color="#000000">ESXi comes in two editions, the vSphere Hypervisor (free version) with limited features and the enterprise ESXI. </font>
- <font color="#000000">The VMware Knowledgebase has best practices for installing and upgrading vSphere 4.1. </font>[<font color="#000000">Installing ESX 4..1 and vCenter 4.1 best practices</font>](< http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1022101>)<font color="#000000"> and </font>[<font color="#000000">Upgrading to ESX 4.1 and vCenter 4.1 best practices</font>](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1022104)<font color="#000000">. </font>
- <font color="#000000">Get yourself familiar with tools as **PowerCLI**, **vCLI** and the **VMware Management Assistant (vMA).**These tools helps you to automate, configure and troubleshoot vSphere 4.1 environments. More information can be found on the following links </font>[<font color="#000000">vCLI</font>](http://www.vmware.com/support/developer/vcli/)<font color="#000000">, </font>[<font color="#000000">PowerCLI</font>](http://www.vmware.com/support/developer/PowerCLI/index.html)<font color="#000000"> and </font>[<font color="#000000">vMA</font>](http://www.vmware.com/support/developer/vima/)<font color="#000000">. </font>
- <font color="#000000">Before upgrading check the Knowlegde Base from VMware for issues with vSphere 4.1. For example </font>[<font color="#000000">Upgrading vCenter Server 4.0 to 4.1 fails with the error: Exception Thrown while executing SQL script</font>](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1025139)<font color="#000000">. </font>

<span mce_style="font-family: &quot;Verdana&quot;,&quot;sans-serif&quot;; font-size: 8pt; mso-bidi-font-family: arial;" style="font-family: "Verdana","sans-serif"; font-size: 8pt"><span style="font-family: verdana"><span style="font-size: xx-small"><span style="color: rgb(0,0,0)"><font size="1">\[ad#verticaal\]</font></span></span></span></span>
