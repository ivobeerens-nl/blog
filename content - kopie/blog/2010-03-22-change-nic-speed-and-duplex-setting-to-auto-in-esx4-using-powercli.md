---
author: Ivo Beerens
categories:
- Uncategorized
date: "2010-03-22T20:24:05Z"
guid: http://www.ivobeerens.nl/?p=537
id: 537
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
title: Change NIC speed and duplex setting to AUTO in ESX4 using PowerCLI
url: /2010/03/22/change-nic-speed-and-duplex-setting-to-auto-in-esx4-using-powercli/
---

When you install VMware ESX 4 by using the default installation method from for example the DVD, the NIC speed and duplex setting are set to fixed for each NIC. This means that the network switch port must be set to fixed too. In VMware ESX 3 the default NIC mode was Auto Negotiate In the vCenter clients this looks like:

 [![image](http://localhost/wp-content/uploads/2010/03/image3_thumb1.png "image")](http://localhost/wp-content/uploads/2010/03/image31.png)

You can easily change the NIC speed and duplex settings to auto Negotiate for all NICs in the ESX host by using PowerCLI. This can be done by using the following one-liner:

Get-VMHostNetworkAdapter | Set-VMHostNetworkAdapter –AutoNegotiate

**Be sure when you execute this command in production environment, that the VMware ESX hosts is in maintenance mode!**

[![image](http://localhost/wp-content/uploads/2010/03/image6_thumb1.png "image")](http://localhost/wp-content/uploads/2010/03/image61.png)

\[ad#verticaal\]
