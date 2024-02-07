---
author: Ivo Beerens
categories:
- ESXi-ARM
- Home Lab
date: "2020-10-21T21:21:56Z"
guid: https://www.ivobeerens.nl/?p=7650
id: 7650
image: /wp-content/uploads/2020/10/h8-scaled.jpg
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_reddit_counts:
- "4"
ssb_total_counts:
- "4"
tags:
- ESXi-ARM
- Home Lab
- Pi
title: How to build an ESXi on ARM Pi cluster?
url: /2020/10/21/how-to-build-an-esxi-on-arm-pi-cluster/
---

Shortly after VMworld 2020, VMware released (after years of announcing and demoing) the ESXi On ARM fling (**\*1)**. On Social media and the community ESXi on ARM is a very hot topic. The ESXi ARM fling makes it possible to run the VMware ESXi hypervisor on ARM platforms such as:

- - Avantek Workstation and server (Ampere eMAG)
    - Lenovo ThinkSystem HR330A and HR350A (Ampere eMAG)
    - SolidRun Honeycomb LX2
    - Raspberry Pi (rPi) 4b model (4GB and 8GB only).

Because it supports the Raspberry Pi 4b model is very interesting for the home labbers.

**(\*1)** A fling shows an early stage of software to the VMware community. There is no official (only community) support available. The ESXi on ARM fling can be download for the following location: [link](https://flings.vmware.com/esxi-arm-edition).

## Use cases

Some use cases for ESXi On ARM are:

- vSAN Witness node, [link](https://www.virtuallyghetto.com/2020/10/vsan-witness-using-raspberry-pi-4-esxi-arm-fling.html)
- Automation environment for PowerCLI and Terraform and packer, [link](https://www.virtuallyghetto.com/2020/10/using-esxi-arm-fling-as-a-lightweight-vsphere-automation-environment-for-powercli-and-terraform.html).
- Security at the edge
- Other home lab projects such as running Home Assistant (blog post is coming).

[![](http://localhost/wp-content/uploads/2020/10/HA-300x149.png)](http://localhost/wp-content/uploads/2020/10/HA.png)

For my home lab environment, I wanted to build an ESXi ARM cluster for my IoT stuff (such as Home Assistant) with two Pi nodes attached to my existing QNAP NAS. With the two ESXi ARM nodes, a vCenter Server, and shared storage, cluster functions such as vMotion, High Availability, DRS, and even FT are available. How cool is that!

Every day there are new use cases created in the community. That’s one reason why ESXi on ARM is such a cool technology!

## My Environment build

Here is a simple diagram of how my setup looks like:

[![](http://localhost/wp-content/uploads/2020/10/Diagram-zonder-titel-300x275.png)](http://localhost/wp-content/uploads/2020/10/Diagram-zonder-titel.png)

## build of materials (BOM)

In this blog article, I will mention the build of materials (BOM). The following components I use:

| **Number** | **Component** | **~Cost €** | **Link (cheapest Pi shop in the Netherlands)** |
|---|---|---|---|
| **1** | Raspberry Pi 4 Model B with 8GB memory. | 87,50 (per Pi) | [Link](https://www.raspberrystore.nl/PrestaShop/raspberry-pi-v4/279-raspberry-pi-4b-8gb-765756931199.html) |
| **2** | Raspberry Pi 15W USB-C Power Supply | 9,95 (per Pi) | [Link](https://www.raspberrystore.nl/PrestaShop/raspberry-pi-v4/230-raspberry-pi-15w-usb-c-power-supply-eu-zwart.html) |
| **3** | Argon One Pi 4 case | 28,95 (per Pi) | [Link](https://www.raspberrystore.nl/PrestaShop/behuizingen/292-argon-one-voor-raspberry-pi-4.html) |
| **4** | Official Raspberry Pi USB keyboard | 17,95 | [Link](https://www.raspberrystore.nl/PrestaShop/home/224-toetsenbord-zwartgrijs-0652508442150.html?search_query=keyboard&results=4) |
| **5** | Micro SD card, 32 GB | 13,95 (per Pi) | [Link](https://www.raspberrystore.nl/PrestaShop/storage-usb-sticks-sd-kaarten/132-micro-sd-kaart-32gb.html) |
| **6** | Delock USB 3.2 16 GB flash drive | 8,99 (per Pi) | I reused the USB drives |
| **7** | Micro-HDMI to HDMI cable 1,5m. | 7,95 | [Link](https://www.raspberrystore.nl/PrestaShop/raspberry-pi-v4/235-hdmi-micro-hdmi-zwart-1m-5412810180363.html) |

**1. Raspberry Pi 4 Model B with 8GB memory**.

This Pi model has the following specifications:

- - 1.5GHz quad-core ARM Cortex-A72 CPU
    - VideoCore VI graphics
    - 4kp60 HEVC decode
    - True Gigabit Ethernet
    - 2 × USB 3.0
    - 2 × USB 2.0 ports
    - 2 × micro-HDMI ports (1 × 4kp60 or 2 × 4kp30)
    - USB-C for input power, supporting 5V 3A operation
    - 8Gb LPDDR4 memory

| [![](http://localhost/wp-content/uploads/2020/10/H1-300x225.jpg)](http://localhost/wp-content/uploads/2020/10/H1-scaled.jpg) | [![](http://localhost/wp-content/uploads/2020/10/H1_1-300x225.jpg)](http://localhost/wp-content/uploads/2020/10/H1_1-scaled.jpg) |
|---|---|

**2. Raspberry Pi 15W USB-C Power Supply**.

The power Supply uses the USB-C for charging the Pi. Make sure to use a decent power supply such as this one.

| [![](http://localhost/wp-content/uploads/2020/10/Power-300x225.jpg)](http://localhost/wp-content/uploads/2020/10/Power-scaled.jpg) |
|---|

**3. Argon One Pi 4 case**

This case (which looks like the Tesla Cybertruck) has an aluminum enclosure for passive cooling and a fan inside for active cooling. Proper cooling is very important for the Pi because when running VMware ESXi it can get hot. You can control the FAN by software or enable the always-on mode. In software mode when the CPU temp reaches 55 degrees, the fan will run at 10%, at 60 degrees it will run at 55%, and at 60 degrees it will run 100%. The driver does not work on VMware ESXi, it is designed for the Pi OS. Hopefully, there will be a VIB available in the future that makes software control of the fan possible. For VMware ESXi, you need to enable the always-on mode by switching the jumper pen next to the fan.

The assembly of the Pi and case is very easy:

- Next to the fan, you see two cooling blocks (grey ones), one for the CPU and the other for the RAM chip
- Add some terminal paste to the cooling blocks
- Plug the PCB board into the Pi and the case. With the PCB board, all the ports and buttons are accessed from the back!
- Tighten the screws.

The GPIO pins are still available when removing the magnetic cap from the top of the case.

| [![](http://localhost/wp-content/uploads/2020/10/C1-300x225.jpg)](http://localhost/wp-content/uploads/2020/10/C1-scaled.jpg) | [![](http://localhost/wp-content/uploads/2020/10/C2-300x225.jpg)](http://localhost/wp-content/uploads/2020/10/C2-scaled.jpg) |
|---|---|
| [![](http://localhost/wp-content/uploads/2020/10/c3_1-300x225.jpg)](http://localhost/wp-content/uploads/2020/10/c3_1-scaled.jpg) | [![](http://localhost/wp-content/uploads/2020/10/C3-300x225.jpg)](http://localhost/wp-content/uploads/2020/10/C3-scaled.jpg) |
| [![](http://localhost/wp-content/uploads/2020/10/Kapje-300x251.jpg)](http://localhost/wp-content/uploads/2020/10/Kapje-scaled.jpg) | [![](http://localhost/wp-content/uploads/2020/10/c4-300x225.jpg)](http://localhost/wp-content/uploads/2020/10/c4-scaled.jpg) |

**4. Official Raspberry Pi USB keyboard**.

This is a 78-key QWERTY keyboard with a built-in 3 ports hub on the back. It has a small form factor.

| [![](http://localhost/wp-content/uploads/2020/10/IMG_8585-300x225.jpg)](http://localhost/wp-content/uploads/2020/10/IMG_8585-scaled.jpg) |
|---|

**5 &amp; 6. Micro SD card and USB disk**.

The SD card is for storing the UEFI firmware that is required to boot the VMware ESXi-ARM installer. I used 32 GB SD. The USB drive is for installing the VMware ESXi ARM ISO.

| [![](http://localhost/wp-content/uploads/2020/10/sdcardslot-300x225.jpg)](http://localhost/wp-content/uploads/2020/10/sdcardslot-scaled.jpg) |
|---|

**7. Micro-HDMI to HDMI cable 1,5m**.

The following components I already have in my home lab environment and will be re-used:

- Netgear switch
- 2 x Delock USB 3.2 16 GB flash drives
- 2 x UTP CAT 5e cables
- QNAP NAS

After the assembly of the case, connect the USB drive, SD card, Power-Supply, Monitor, keyboard, UTP cable, and you’re ready to install the VMware ESXi for ARM fling.

| [![](http://localhost/wp-content/uploads/2020/10/Naast-300x165.jpg)](http://localhost/wp-content/uploads/2020/10/Naast-scaled.jpg) |
|---|

In the next ESXi on ARM blog, I will highlight the ESXi on ARM installation process and how to install and configure Home Assistant.

Here are some great links to follow:

- [ESXi ARM Fling](https://flings.vmware.com/esxi-arm-edition)
- [ESXi-ARM VMTN forum](https://communities.vmware.com/community/vmtn/vsphere/esxi/esxi-arm-fling)
- [VMware ESXI-ARM blog](https://blogs.vmware.com/arm)
- [William Lam ESXi-ARM](https://www.virtuallyghetto.com/category/esxi-arm)
- [The slack channel #esxi-arm on VMware{code}](https://code.vmware.com/web/code/join)
- [ESXi-ARM Twiiter](https://twitter.com/esxi_arm)

Thanks to the [Raspberry Store ](https://www.raspberrystore.nl/PrestaShop/)for the quick delivery.
