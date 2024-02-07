---
author: Ivo Beerens
categories:
- hardware
- Home Lab
- homebrew
- Hyper-V
- vSphere
- Whitebox
- windows server 2012
date: "2012-03-13T12:53:56Z"
guid: http://www.ivobeerens.nl/?p=1419
id: 1419
ssb_fbshare_counts:
- "3"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:3;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "3"
tags:
- hardware
- homebrew
- hyper-v
- vSphere
- Whitebox
- windows server 2012
title: Intel X79 whitebox for vSphere 5 and Hyper-V 3
url: /2012/03/13/intel-x79-whitebox-for-vsphere-5-and-hyper-v-3/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

<font color="#000000">Updates:</font>

<font color="#ff0000">Update August 8 2012</font><font color="#000000">: Added Microsoft Windows 2012 Hyper-V screenshots and link to blog post how to enable the Intel 82579V NIC</font>

<font color="#ff0000">Update August 9 2012</font>: Updating to the latest BIOS enables support for DirectPath I/O in VMware vSphere. Screenshot added

<font color="#000000">In an earlier blog post (found </font>[<font color="#000000">here</font>](http://localhost/2011/11/18/time-for-new-whitebox-for-your-vmware-vsphere-or-ms-hyper-v-home-lab-environment/)<font color="#000000">) I mentioned that it is time for a new homebrew whitebox based on the Intel X79 chipset. With the X79 chipset it is possible to install 64GB of memory (8 x 8 GB). Because the 8 GB DIMMs are expensive on the moment, I decided to use 8 x 4GB DIMMs (total 32GB). </font>

<font color="#000000">I decided to create one physical host for testing VMware vSphere 5, vCloud Director, VMware SRM, VMware View 5 etc. The possibility to create a physical ESXi5 server, create virtual ESXi hosts on it and start VM on the virtual hosts is great! This feature is called nesting. How to do this, can be found on William Lam blog found </font>[<font color="#000000">here</font>](http://www.virtuallyghetto.com/2011/07/how-to-enable-support-for-nested-64bit.html)<font color="#000000">.</font>

### <font color="#000000">Components used for the VMware ESXi 5 / Microsoft Windows Server 2012 whitebox:</font>

- <font color="#000000">Intel i7-3820 CPU 3.60 GHz, 4 cores, with Hyper threading 8 cores </font>
- <font color="#000000">Zalman CNPS10X performance cooler</font>
- <font color="#000000">Asus P9X79 s2011 motherboard. Some specs:</font>
    - <font color="#000000">Socket 2011</font>
    - <font color="#000000">8 DIMM slots, supports 64GB memory</font>
    - <font color="#000000">Expansions slots: 2 x PCIe 3.0 (dual x16), 1 x PCIe (x8 mode), 2 x PCIe 2.0 x1, 1 x PCI</font>
    - <font color="#000000">2 SATA 6 Gb/s port, 4 x SATA 3 Gb/s </font>
    - <font color="#000000">LAN: Intel 82579V Gigabit LAN controller</font>
- <font color="#000000">2 x Corsair Vengeance DDR3- 1600 16GB (4 x 4) kit, total 32GB memory (max 64GB)</font>

<font color="#000000"></font>

<font color="#000000">The case, power supply, graphical card, RAID controller and extra NIC(S) are reused. Here are some photos of the configuration:</font>

<font color="#000000"></font>

| [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/03/image_thumb10.png "image")</font>](http://localhost/wp-content/uploads/2012/03/image10.png) | [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/03/image_thumb11.png "image")</font>](http://localhost/wp-content/uploads/2012/03/image11.png) |
|---|---|
| [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/03/image_thumb12.png "image")</font>](http://localhost/wp-content/uploads/2012/03/image12.png) | [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/03/image_thumb13.png "image")</font>](http://localhost/wp-content/uploads/2012/03/image13.png) |
| [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/03/image_thumb14.png "image")</font>](http://localhost/wp-content/uploads/2012/03/image14.png) | <font color="#000000"></font> |

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000">When the hardware configuration was done and tried to power on the system, nothing happened (black screen). The appears that BIOS of the motherboard didn’t know the i7-3820 CPU yet. The cool thing is that the motherboard has a function called “USB BIOS Flashback”. It is possible to flash the BIOS without CPU or memory installed. Here are the steps:</font>

- <font color="#000000">Download the latest BIOS from the Asus site;</font>
- <font color="#000000">Extract the BIOS on a USB stick;</font>
- <font color="#000000">Rename the BIOS file, example: rename “P9X79-ASUS-0906.ROM” in “P9X79.ROM” (**important**);</font>
- <font color="#000000">Place the USB stick in the USB port with the WHITE interior on the back;</font>
- <font color="#000000">Press the BIOS flashback button for 3 seconds and the light will begin to flash;</font>
- <font color="#000000">Don’t turn of the computer during the BIOS flash; </font>
- <font color="#000000">When the flashing light stop, the BIOS has been complete; </font>

<font color="#000000"></font>

<font color="#000000">After the BIOS update was finished, the system boots and I was able to install VMware ESXi and Windows Server 2012 and enable the Hyper-V role.</font>

### <font color="#000000">vSphere 5 / ESXi 5 screenshots:</font>

| [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/03/image_thumb15.png "image")</font>](http://localhost/wp-content/uploads/2012/03/image15.png) | [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/03/image_thumb16.png "image")</font>](http://localhost/wp-content/uploads/2012/03/image16.png) |
|---|---|
| <font color="#000000">Hyper threading enables 8 cores</font> | <font color="#000000">32GB memory</font> |
| [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/03/image_thumb17.png "image")</font>](http://localhost/wp-content/uploads/2012/03/image17.png) | [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/03/image_thumb18.png "image")</font>](http://localhost/wp-content/uploads/2012/03/image18.png) |
| <font color="#000000">The onboard SATA controller is listed as Patsburg 6 Port SATA AHCI controller. Software-RAID does not work  The hardware RAID controller is added as extra PCI card  </font> | <font color="#000000">The onboard Intel 82579V NIC is not supported in ESXi5. Use the procedure found </font>[<font color="#000000">here</font>](http://localhost/2011/12/13/vmware-esxi-5-whitebox-nic-support/)<font color="#000000"> to add the NIC. Use at your own risk! The Intel 82574L NIC is added as extra PCIe card.  </font> |
| [![image](http://localhost/wp-content/uploads/2012/08/image_thumb19.png "image")](http://localhost/wp-content/uploads/2012/08/image20.png)The latest firmware includes support for DirectPath I/O |  |

<font color="#000000"></font>

### <font color="#000000">Microsoft Windows Server 2012</font>

It is possible to install Microsoft Windows 2012 and enable the Hyper-V role. Here are some screenshots:

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

| [![image](http://localhost/wp-content/uploads/2012/08/image_thumb11.png "image")](http://localhost/wp-content/uploads/2012/08/image11.png) | [![image](http://localhost/wp-content/uploads/2012/08/image_thumb12.png "image")](http://localhost/wp-content/uploads/2012/08/image12.png)<font color="#000000"></font> |
|---|---|
| [![image](http://localhost/wp-content/uploads/2012/08/image_thumb13.png "image")](http://localhost/wp-content/uploads/2012/08/image14.png)<font color="#000000"></font> | [![image](http://localhost/wp-content/uploads/2012/08/image_thumb14.png "image")](http://localhost/wp-content/uploads/2012/08/image15.png)<font color="#000000"></font> |

<font color="#000000">The onboard Intel 82579V NIC is not recognized in Windows Server 2012 by default. How-to enable the Intel 82579V NIC is explained in this explained in this [blog](http://localhost/2012/08/08/enable-the-intel-82579v-nic-in-windows-server-2012/) post.</font>

<font color="#000000">This whitebox is a great extension to my home lab! </font>

\[ad#banner\]
