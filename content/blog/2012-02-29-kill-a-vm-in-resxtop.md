---
author: Ivo Beerens
categories:
- ESXi
- esxtop
date: "2012-02-29T12:17:32Z"
guid: http://www.ivobeerens.nl/?p=1316
id: 1316
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- esxi
- esxtop
title: 'Quick tip: How to kill a VM with esxtop'
url: /2012/02/29/kill-a-vm-in-resxtop/
---

<span style="color: #000000;">There are different ways to kill a unresponsable VM by using the vCLI or the console. </span><span style="color: #000000;">In VMware ESXi, it is possible to kill a running VM process by using esxtop or resxtop. For VMware ESXi you need to enter Tech Support Mode (TSM) first to run esxtop.</span>

<span style="color: #000000;">The following procedure can be used to kill a VM (The bold text are the commands to enter):</span>

- <span style="color: #000000;">**esxtop**</span>
- <span style="color: #000000;">Press **c** for the CPU resource screen</span>
- <span style="color: #000000;">Press **shift + V** to display VMs only</span>
- <span style="color: #000000;">Press **f** to change the display fields </span>

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/02/image_thumb13.png "image")</span>](http://localhost/wp-content/uploads/2012/02/image15.png)

- <span style="color: #000000;">Press **c** to select the LWID (Leader World Id) and press **enter**</span>
- <span style="color: #000000;">Identify the VM by it’s LWID </span>
- <span style="color: #000000;">Press **k** </span>
- <span style="color: #000000;">Enter the **LWID** of the VM to kill and press enter</span>
- <span style="color: #000000;">Wait for 30 seconds and validate that the VM is no longer listed</span>
