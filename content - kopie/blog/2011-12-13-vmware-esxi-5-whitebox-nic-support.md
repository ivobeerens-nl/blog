---
author: Ivo Beerens
categories:
- ESXi
- Home Lab
- Whitebox
date: "2011-12-13T16:44:34Z"
guid: http://www.ivobeerens.nl/2011/12/13/vmware-esxi-5-whitebox-nic-support/
id: 1182
ssb_fbshare_counts:
- "12"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:12;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "12"
tags:
- esxi
- homebrew
- Whitebox
title: VMware ESXi 5 whitebox NIC support
url: /2011/12/13/vmware-esxi-5-whitebox-nic-support/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

<span style="color: #000000;">I tested the NICs below in my VMware ESXi 5.x whitebox server at home. Here the status:</span>

| **<span style="color: #000000;">NIC </span>** | **<span style="color: #000000;">Recognized by VMware ESXi 5</span>** | **<span style="color: #000000;">Listed in ESXi 5 as</span>** |
|---|---|---|
| <span style="color: #000000;">Intel PRO/1000GT Desktop Adapter PCI</span> | <span style="color: #000000;">Yes</span> | <span style="color: #000000;">Intel 82541PI Gigabit Ethernet Controller</span> |
| <span style="color: #000000;">Realtek RTL 8111E</span> | <span style="color: #000000;">Yes</span> | <span style="color: #000000;">Realtek 8168 Gigabit Ethernet</span> |
| <span style="color: #000000;">Intel Gigabit CT Desktop Adapter PCI-e</span> | <span style="color: #000000;">Yes</span> | <span style="color: #000000;">Intel Corporation 82574L</span> |
| <span style="color: #000000;">Intel 82579 Gigabit LAN controller</span> | <span style="color: #000000;"><span style="color: #000000;">**No**    You need the make a customized ESXi 5 ISO or VIB file.</span></span>This is a not supported configuration! | <span style="color: #000000;"><span style="color: #000000;">Intel Corporation 82579V </span></span>orIntel Corporation 82579LM |

<span style="color: #000000;">To add for example the Intel 82579 chipset, create a customized ESXi 5 ISO. This is very simple because some people have already done the </span><span style="color: #000000;">hard work. </span>

<span style="color: #000000;">Here are the steps: </span>

<span style="color: #000000;">1. Download ESXi-Customizer (create by Andreas Peetz) found </span><span style="color: #000000;">here</span><span style="color: #000000;">.</span>

<span style="color: #000000;">2. Download the driver (created by Chilly) found </span><span style="color: #000000;">here</span><span style="color: #000000;">.</span>

<span style="color: #000000;">3. Start the ESXi-Customizer and follow the 3 steps:</span>

[![2011-12-04 17h03_20](http://localhost/wp-content/uploads/2011/12/2011-12-04-17h03_20_thumb.jpg "2011-12-04 17h03_20")](http://localhost/wp-content/uploads/2012/01/2011-12-04-17h03_201.jpg)

<span style="color: #000000;">And you’re ready to create the customized VMware ESXi 5 ISO. The ISO supports the Intel 82579V and 82579LM NIC(s) found on many whitebox motherboards today. </span><span style="color: #000000;">Possible future updated version(s) of the driver can be found in the following </span>[<span style="color: #000000;">post</span>](http://hardforum.com/showthread.php?t=1607992)<span style="color: #000000;">.</span>
