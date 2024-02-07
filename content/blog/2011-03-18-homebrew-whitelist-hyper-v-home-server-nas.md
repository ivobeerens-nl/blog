---
author: Ivo Beerens
categories:
- homebrew
- Hyper-V
- server
- Startwind
- VMware
date: "2011-03-18T12:30:46Z"
guid: http://www.ivobeerens.nl/?p=804
id: 804
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- homebrew
- hyper-v r2
- server
- Startwind
- VMware
title: Homebrew / Whitelist Hyper-V R2 home server NAS
url: /2011/03/18/homebrew-whitelist-hyper-v-home-server-nas/
---

<font color="#000000">For my home lab i was looking for a home server with NAS functionality. My current Iomega IX2 (2x500GB) NAS is replaced by this server. For this server I had the following requirements:</font>

- <font color="#000000">Low power consumption (24×7) </font>
- <font color="#000000">Low noise </font>
- <font color="#000000">Flexibly and room to expand with extra hard drive(s), hardware RAID and a NIC </font>
- <font color="#000000">Home server functionality for sharing photos, music, documents and films </font>
- <font color="#000000">NAS functionality with iSCSI and NFS protocol </font>
- <font color="#000000">FTP server </font>
- <font color="#000000">Hypervisor enabled </font>
- <font color="#000000">Backup server </font>
- <font color="#000000">Print server </font>
- <font color="#000000">Active Directory </font>
- <font color="#000000">DNS server </font>
- <font color="#000000">Download server </font>
- <font color="#000000">Wake-on-LAN functionality to start other virtualization hosts </font>

<font color="#000000">I selected the following components:</font>

#### **<font color="#000000">Motherboard</font>**

<font color="#000000">Asus E35M1-M Pro. This motherboard contains AMD Zacate E-350 1.60 GHz Dual-Core Processor. It has TDP (Thermal Design Power) of **18W**!</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/03/image_thumb.png "image")</font>](http://localhost/wp-content/uploads/2011/03/image.png)

**<font color="#000000">Specifications:</font>**

- <font color="#000000">Dual-core 1.60 GHz processor that has passive cooling. </font>
- <font color="#000000">Onboard AMD Radeon graphic card </font>
- <font color="#000000">USB 3.0 </font>
- <font color="#000000">5 x SATA 6Gb/s </font>
- <font color="#000000">EFI BIOS </font>
- <font color="#000000">2 x DIMM, Max 8GB RAM </font>
- <font color="#000000">Realtek Gigabit 8111E LAN </font>
- <font color="#000000">1 x PCI Express 2.0, 1 x PCI Express 2.0 x1 slot, 2 x PCI 3.0 slots </font>
- <font color="#000000">uATX Form Factor, 9.6 inch x 7.2 inch ( 24.4 cm x 18.3 cm ) </font>

<font color="#000000">This Motherboard has room to expand, it is possible to add extra extra hard drive(s), a RAID controller and an extra NIC. Virtualization is also supported with AMD-V feature in the CPU. </font>

**<font color="#000000"></font>**

#### <font color="#000000">**Memory** </font>

<font color="#000000">The motherboard supports two single channel DDR3 1066MHz DIMMS . The maximum memory is 8GB.</font>

<font color="#000000"></font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/03/image_thumb1.png "image")</font>](http://localhost/wp-content/uploads/2011/03/image1.png)

<font color="#000000"></font>

<font color="#000000">I picked 2 x 4 GB G.Skill Ripjaws (F3-10666CL9D-8GBRL ). More supported memory for this motherboard can be found in the Asus </font>[<font color="#000000">download</font>](http://www.asus.com/product.aspx?P_ID=qSoDxhM5mAk1F607)<font color="#000000"> section</font>

<font color="#000000"></font>

|  |  |  #### **<font color="#000000">Hard drives</font>**

<font color="#000000">In this set-up I used three hard-drives. As boot drive an old Samsung SP0411C 40GB SATA 150 is used. For the data and backup storage I picked 2 Samsung EcoGreen F4EG 2TB hard drives. </font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/03/image_thumb2.png "image")</font>](http://localhost/wp-content/uploads/2011/03/image2.png)

**<font color="#000000"></font>**

<font color="#000000">Some specifications:</font>

- <font color="#000000">2TB unformatted capacity   
    SATA 3Gb/s interface </font>
- <font color="#000000">Three platter design </font>
- <font color="#000000">32MB cache </font>
- <font color="#000000">5400RPM spin speed </font>
- <font color="#000000">Average Seek time – 8.9 ms </font>

<font color="#000000">Great price, large space and low power consumption.</font>

#### **<font color="#000000">Power Supply</font>**

<font color="#000000">As Power Supply I choose the Seasonic S12II-330W ATX power supply. </font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/03/image_thumb3.png "image")</font>](http://localhost/wp-content/uploads/2011/03/image3.png)

<font color="#000000"></font>

<font color="#000000">Some specifications:</font>

- <font color="#000000">80 PLUS </font>
- <font color="#000000">Efficiency up to 85% </font>
- <font color="#000000">Advanced ultra-low resistance, high temperature capacitors on critical 12V rail </font>
- <font color="#000000">Low Noise </font>

<font color="#000000">Good quality, high efficiency (85%) and quiet power supply.</font>

**<font color="#000000"></font>**

#### **<font color="#000000">Case</font>**

<font color="#000000">Cooler Master CM 690 II Advanced </font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/03/image_thumb4.png "image")</font>](http://localhost/wp-content/uploads/2011/03/image4.png)

<font color="#000000">Some specifications:</font>

- <font color="#000000">Tower </font>
- <font color="#000000">Motherboard support Micro – ATX / ATX / Mini-ITX </font>
- <font color="#000000">6 x 3,5” bays </font>
- <font color="#000000">4 x 2,5”bays </font>
- <font color="#000000">Dimension (W / H / D) 214.5 x 496 x 528.8 mm / 8.4 x 19.5 x 20.8 inch </font>
- <font color="#000000">Cable management </font>

<font color="#000000">Great case with a lot of room for expanding.</font>

**<font color="#000000"></font>**

#### **<font color="#000000">Software running so far</font>**

<font color="#000000">When installing VMware ESXi it gives an error because the NIC and disk controller aren’t supported. The solution is to install a controller and NIC that are supported or add the drivers to the VMware ESXi ISO (more information can be found </font>[<font color="#000000">here</font>](http://www.vm-help.com/index.html)<font color="#000000">). </font>

<font color="#000000">An easier way is to use Microsoft Hyper-V R2 because all the drivers are supported. </font>

<font color="#000000">The following software is installed so far:</font>

- <font color="#000000">Windows 2008 R2 SP1 with the AD, DNS and Hyper-V role installed </font>
- <font color="#000000">Windows Home Server 2011 (Vail) RC as Virtual Machine (VM) for sharing photos, documents, music and videos. I use it also to backup my work laptop and other Windows pc’s at home. </font>
- <font color="#000000">Starwind iSCSI SAN </font>
- <font color="#000000">Services for Network File System for the NFS protocol </font>
- <font color="#000000">FileZilla server for FTP </font>

<font color="#000000"></font>

#### <font color="#000000" style="font-weight: bold">Power consumption</font>

<font color="#000000">Here are some power consumption tests I did:</font>

- <font color="#000000">Motherboard with 8GB RAM, started in the EFI BIOS without the hard drives attached. Power consumption around **31 Watt** </font>
- <font color="#000000">Motherboard with 8GB RAM with three hard drives attached , Windows 2008 R2 with the MS Hyper-V R2 role and one VM active. Power consumption idle around **35 Watt** </font>
- <font color="#000000">Motherboard with 8GB RAM with three hard drives attached, Windows 2008 R2 with the MS Hyper-V R2 role and one VM active and 2 CPU cores fully loaded in Windows 2008 R2. Power consumption around **45 Watt** </font>

#### <font color="#000000" style="font-weight: bold">Performance</font>

<font color="#000000">Don’t except that this configuration is a performance monster. The performance is not bad for a home server with a lot of flexibility, low noise and power consumption and couple of VMs running. </font>

<font color="#000000">Screenshot Hyper-V manager with Microsoft Windows Home Server 2011 running.</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/03/image_thumb5.png "image")</font>](http://localhost/wp-content/uploads/2011/03/image5.png)<font color="#000000"> </font>

<font color="#000000"></font>

#### **<font color="#000000">Considerations</font>**

<font color="#000000">The following considerations (will increase the costs) can be made for better performance and/or lower consumption:</font>

- <font color="#000000">Use an SSD drive as boot hard drive for faster booting and lower power consumption. </font>
- <font color="#000000">Change the power supply for an higher efficiency power supply. For example a PicoPSU has an higher efficiency for lower power consumption. </font>
- <font color="#000000">Add an RAID card with cache on it for better disk performance. The power consumption will increase. </font>

<font color="#000000"></font>

<font color="#000000"></font>

\[ad#banner\]
