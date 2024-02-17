---
title: "VMware ESXi 5 whitebox supported motherboard"
date: "2011-09-01T14:05:50.000Z"
categories: 
  - "whitebox"
tags: 
  - "homebrew"
  - "whitebox"
---

If you want a low power consumption whitebox motherboard to run some VMs that are not resource intensive the Asus E35M1-M PRO Zacate motherboard is an option. It has an AMD E-350 dual core 1,6 GHz processor with passive cooling, onboard graphics, max 8GB memory support, onboard LAN and 5x SATA 6 onboard. And it’s cheap.

I test the Asus E35M1-M PRO Zacate motherboard in my home lab, and it will run for VMware ESXi 5.0.0 build 469512. This motherboard can be used in a homebrew server.

**Specifications Asus E35M1-M PRO Zacate motherboard:**

[![image](images/image_thumb.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/09/image.png)

<table border="0" cellspacing="0" cellpadding="2" width="400"><tbody><tr><td valign="top" width="200"><strong><font color="#000000">Form factor</font></strong></td><td valign="top" width="200"><font color="#000000">uATX</font></td></tr><tr><td valign="top" width="200"><strong><font color="#000000">CPU</font></strong></td><td valign="top" width="200"><font color="#000000">AMD Fusion E-350 Dual-core onboard processor with passive cooler</font></td></tr><tr><td valign="top" width="200"><strong><font color="#000000">Memory</font></strong></td><td valign="top" width="200"><font color="#000000">Corsair XMS3 DDR3,1333-8GB KIT (2x4GB)</font></td></tr><tr><td valign="top" width="200"><strong><font color="#000000">Graphics</font></strong></td><td valign="top" width="200"><font color="#000000">Onboard integrated ATI Radeon HD 6310 GPU</font></td></tr><tr><td valign="top" width="200"><strong><font color="#000000">Storage</font></strong></td><td valign="top" width="200"><font color="#000000">5 x SATA 6 Gb/s</font></td></tr><tr><td valign="top" width="200"><strong><font color="#000000">LAN</font></strong></td><td valign="top" width="200"><font color="#000000">1 x Realtek 8111E , 1 x Gigabit LAN Controller</font></td></tr><tr><td valign="top" width="200"><strong><font color="#000000">USB ports</font></strong></td><td valign="top" width="200"><font color="#000000">2 x USB ports<br>12 x USB 2. ports</font></td></tr><tr><td valign="top" width="200"><strong><font color="#000000">BIOS</font></strong></td><td valign="top" width="200"><font color="#000000">32 Mb flash ROM UEFI</font></td></tr><tr><td valign="top" width="200"><strong><font color="#000000">More information about the specifications</font></strong></td><td valign="top" width="200"><font color="#000000">Asus website</font></td></tr></tbody></table>

Here are some screenshots from the vSphere Client:

**VMware ESXi 5.0.0 DCUI**

[![image](images/image_thumb1.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/09/image1.png)

**Summary page**

[![image](images/image_thumb2.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/09/image2.png)

**Example of the processor load with 2 x MS Windows 2008 R2 VMs**

[![image](images/image_thumb9.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/09/image10.png)

**Onboard processor**

[![image](images/image_thumb3.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/09/image3.png)

**Memory**

[![image](images/image_thumb4.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/09/image4.png)

**Onboard disk controllers**

[![image](images/image_thumb5.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/09/image5.png)

**The Realtek onboard LAN adapter.**

[![image](images/image_thumb6.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/09/image6.png)

In VMware ESX|(i) 4.x the Realtek LAN adapter is not supported.

**Power consumption**

The following configuration is used:

> \- Asus E35M1-M Pro
> 
> \- Corsair XMS3 DDR3,1333-8GB KIT (2 x 4GB memory)
> 
> \- OCZ Vertex Plus - 60GB - 2.5inch
> 
> \- Be Quiet! Pure Power L7 300W
> 
> \- Hypervisor VMware ESXi 5

Here are some test I did:

> \- Startup VMware ESXi 5 30 Watt
> 
> \- Idle with two Microsoft Windows 2008 R2 VMs 25 Watt
> 
> \- One Microsoft Windows 2008 R2 VM with 100% (using the cpubusy.vbs script) processor load 28 Watt
> 
> \- Two Microsoft Windows 2008 R2 VM with 100% (using the cpubusy.vbs script) processor load between 30 and 32 Watt

To power consumption is not bad if you want to run a couple of VMs 24x7.

**Updated:**

18 September 2011: added processor load and power consumption examples

\[ad#banner\]
