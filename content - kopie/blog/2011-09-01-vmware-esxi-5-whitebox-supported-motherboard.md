---
author: Ivo Beerens
categories:
- Whitebox
date: "2011-09-01T16:05:50Z"
guid: http://www.ivobeerens.nl/?p=1032
id: 1032
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- homebrew
- Whitebox
title: VMware ESXi 5 whitebox supported motherboard
url: /2011/09/01/vmware-esxi-5-whitebox-supported-motherboard/
---

<font color="#000000"></font>

<font color="#000000">If you want a low power consumption whitebox motherboard to run some VMs that are not resource intensive the Asus E35M1-M PRO Zacate motherboard is an option. It has an AMD E-350 dual core 1,6 GHz processor with passive cooling, onboard graphics, max 8GB memory support, onboard LAN and 5x SATA 6 onboard. And it’s cheap.</font>

<font color="#000000">I test the Asus E35M1-M PRO Zacate motherboard in my home lab, and it will run for VMware ESXi 5.0.0 build 469512. <font color="#000000">This motherboard can be used in a homebrew server.</font></font>

<font color="#000000"> </font>

**<font color="#000000"></font>**

**<font color="#000000">Specifications Asus E35M1-M PRO Zacate motherboard:</font>**

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/09/image_thumb.png "image")</font>](http://localhost/wp-content/uploads/2011/09/image.png)

<font color="#000000"></font>

<font color="#000000"></font>

| **<font color="#000000">Form factor</font>** | <font color="#000000">uATX </font> |
|---|---|
| **<font color="#000000">CPU</font>** | <font color="#000000">AMD Fusion E-350 Dual-core onboard processor with passive cooler</font> |
| **<font color="#000000">Memory</font>** | <font color="#000000">Corsair XMS3 DDR3,1333-8GB KIT (2x4GB)</font> |
| **<font color="#000000">Graphics</font>** | <font color="#000000">Onboard integrated ATI Radeon HD 6310 GPU</font> |
| **<font color="#000000">Storage</font>** | <font color="#000000">5 x SATA 6 Gb/s</font> |
| **<font color="#000000">LAN</font>** | <font color="#000000">1 x Realtek 8111E , 1 x Gigabit LAN Controller</font> |
| **<font color="#000000">USB ports</font>** | <font color="#000000">2 x USB ports    12 x USB 2. ports</font> |
| **<font color="#000000">BIOS</font>** | <font color="#000000">32 Mb flash ROM UEFI</font> |
| **<font color="#000000">More information about the specifications</font>** | <font color="#000000">Asus website</font> |

<font color="#000000"></font>

<font color="#000000">Here are some screenshots from the vSphere Client:</font>

<font color="#000000"></font>

**<font color="#000000">VMware ESXi 5.0.0 DCUI</font>**

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/09/image_thumb1.png "image")</font>](http://localhost/wp-content/uploads/2011/09/image1.png)

**<font color="#000000">Summary page</font>**

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/09/image_thumb2.png "image")</font>](http://localhost/wp-content/uploads/2011/09/image2.png)

<font color="#000000">**Example of the processor load with 2 x MS Windows 2008 R2 VMs**</font>

[![image](http://localhost/wp-content/uploads/2011/09/image_thumb9.png "image")](http://localhost/wp-content/uploads/2011/09/image10.png)

**<font color="#000000">Onboard processor</font>**

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/09/image_thumb3.png "image")</font>](http://localhost/wp-content/uploads/2011/09/image3.png)

**<font color="#000000">Memory</font>**

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/09/image_thumb4.png "image")</font>](http://localhost/wp-content/uploads/2011/09/image4.png)

<font color="#000000"></font>

**<font color="#000000">Onboard disk controllers</font>**

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/09/image_thumb5.png "image")</font>](http://localhost/wp-content/uploads/2011/09/image5.png)

**<font color="#000000">The Realtek onboard LAN adapter.</font>**

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/09/image_thumb6.png "image")</font>](http://localhost/wp-content/uploads/2011/09/image6.png)

<font color="#000000">In VMware ESX|(i) 4.x the Realtek LAN adapter is not supported.</font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000">**Power consumption**</font>

<font color="#000000"></font>

<font color="#000000">The following configuration is used:</font>

> <font color="#000000">– Asus E35M1-M Pro</font>
> 
> <font color="#000000">– Corsair XMS3 DDR3,1333-8GB KIT (2 x 4GB memory)</font>
> 
> <font color="#000000">– OCZ Vertex Plus – 60GB – 2.5inch</font>
> 
> <font color="#000000">– Be Quiet! Pure Power L7 300W </font>
> 
> <font color="#000000">– Hypervisor VMware ESXi 5</font>

<font color="#000000"></font>

<font color="#000000">Here are some test I did:</font>

> <font color="#000000">– Startup VMware ESXi 5 30 Watt</font>
> 
> <font color="#000000">– Idle with two Microsoft Windows 2008 R2 VMs 25 Watt</font>
> 
> <font color="#000000">– One Microsoft Windows 2008 R2 VM with 100% (using the cpubusy.vbs script) processor load 28 Watt</font>
> 
> <font color="#000000">– Two Microsoft Windows 2008 R2 VM with 100% (using the cpubusy.vbs script) processor load between 30 and 32 Watt</font>

<font color="#000000"></font>

<font color="#000000">To power consumption is not bad if you want to run a couple of VMs 24×7.</font>

<font color="#000000"></font>

<font color="#000000">**Updated:**</font>

<font color="#000000">18 September 2011: added processor load and power consumption examples </font>

<font color="#000000"> </font>

\[ad#banner\]
