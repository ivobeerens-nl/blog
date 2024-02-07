---
author: Ivo Beerens
categories:
- troubleshooting
- VMware
- vSphere
date: "2010-08-20T12:41:52Z"
guid: http://www.ivobeerens.nl/?p=575
id: 575
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- troubleshooting
- VMware
- vSphere
title: VMs with dropped packets %DRPRX
url: /2010/08/20/vms-with-dropped-packets-drprx/
---

<font color="#000000"></font>

<font color="#000000">During a health check of a vSphere environment i notices dropped packets on several VMs. In ESXTOP the **%DRPRX** value showed dropped receive packets on several VMs. In the screenshot an example:</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2010/08/image_thumb.png "image")</font>](http://localhost/wp-content/uploads/2010/08/image.png)<font color="#000000"> </font>

<span id="main" style="visibility: visible"><span id="search" style="visibility: visible"><font color="#000000">The customer uses vSphere 4.0 build 244038. All the VMs that experiencing the dropped packets problem were Windows 2008 with an **E1000** NIC. </font></span></span>

> <span style="visibility: visible"><span style="visibility: visible"><font color="#000000"><span style="font-family: arial; font-size: 10pt">**E1000** — An emulated version of the Intel 82545EM Gigabit Ethernet NIC. A driver for this NIC is not included with all guest operating systems. Typically Linux versions 2.4.19 and later, Windows XP Professional x64 Edition and later, and Windows Server 2003 (32-bit) and later include the E1000 driver.</span></font></span></span>

<span style="visibility: visible"><span style="visibility: visible"><font color="#000000">On of the Windows 2008 VMs had no packets drops. The only difference with the other VMs was that the IPv6 protocol binding on the NIC was disabled. After disabling the IPv6 protocol binding on all the other VMs the packet drops is disappear.</font></span></span>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2010/08/image_thumb1.png "image")</font>](http://localhost/wp-content/uploads/2010/08/image1.png)<font color="#000000"> </font>

<font color="#000000">Some services require the IPv6 binding, so disabling the IPv6 binding was no option for the customer. All the other Windows 2008 machines with the VMXNET3 NIC and IPv6 enabled had no packet drops. After changing all the VMs with Windows 2008 and the E1000 NIC to the VMXNET3 NIC solves the problem. </font>

> <span style="font-family: arial; font-size: 10pt"><font color="#000000">The VMXNET 3 adapter is the next generation of a paravirtualized NIC designed for performance, and is not related to VMXNET or VMXNET 2. It offers all the features available in VMXNET 2, and adds several new features like multiqueue support (also known as Receive Side Scaling in Windows), IPv6 offloads, and MSI/MSI-X interrupt delivery.</font></span>

<font color="#000000">Whenever possible i suggest to use the VMXNET3 driver for Windows 2008 Operating Systems.</font>

<font color="#000000" size="1"><span mce_style="font-family: &quot;Verdana&quot;,&quot;sans-serif&quot;; font-size: 8pt; mso-bidi-font-family: arial;" style="font-family: "Verdana","sans-serif"; font-size: 8pt"><span mce_style="font-family: verdana;" style="font-family: verdana"><span mce_style="font-size: xx-small;" style="font-size: xx-small"><span mce_style="color: #000000;" style="color: rgb(0,0,0)"><span style="font-size: xx-small">\[ad#verticaal\]</span></span></span></span></span></font>
