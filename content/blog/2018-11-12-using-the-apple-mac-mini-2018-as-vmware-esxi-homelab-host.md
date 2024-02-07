---
author: Ivo Beerens
categories:
- Home Lab
- Mac Mini
date: "2018-11-12T15:12:41Z"
guid: https://www.ivobeerens.nl/?p=6419
id: 6419
image: /wp-content/uploads/2018/11/0A1868CA-4AA9-4C85-A23F-F10FB515DEE0-e1542027369403.jpeg
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
tags:
- esxi
- mac
title: Using the Apple Mac Mini 2018 as VMware ESXi homelab host
url: /2018/11/12/using-the-apple-mac-mini-2018-as-vmware-esxi-homelab-host/
---

Begin November Apple released there new Apple Mini 2018 models. The last Mac Mini was from 2014. My first question: Is it possible to use the new Mac Mini 2018 as VMware ESXi host? So I’ve borrowed a Mac Mini 2018 model with the following specifications:

- Mac Mini 2018,
- CPU: Intel Core i3 3.6 GHz 4-core 6MB shared L3 cache
- Memory: 8 GB
- Disk: 128 GB SSD storage
- 1 Gb Ethernet adapter

[![](http://localhost/wp-content/uploads/2018/11/2D86F49B-948E-4B2C-A807-037CA46A0069-300x225.jpeg)](http://localhost/wp-content/uploads/2018/11/2D86F49B-948E-4B2C-A807-037CA46A0069.jpeg) [![](http://localhost/wp-content/uploads/2018/11/3442A112-7EBB-44FA-8DB6-EF9555AB602D-300x225.jpeg)](http://localhost/wp-content/uploads/2018/11/3442A112-7EBB-44FA-8DB6-EF9555AB602D.jpeg)

The new Apple Mini 2018 comes in two basic configurations. The basic configurations can be changed (CPU, memory, disk and Ethernet adapter) during the ordering process.

**Model comparison**:

|  | **Models** | **Models** |
|---|---|---|
| **Processor** | Intel Core i3 3.6 GHz 4-core 6MB shared L3 cache **configurable to**:  Intel Core i7 3.2 GHz 6-core Turbo Boos 4.6 GHz 12MB shared L3 cache. | Intel Core i5 3.0 GHz 6 core Turbo Boost up to 4.1GHz 9MB shared L3 cache **configurable to:**  Intel Core i7 3.2 GHz 6-core Turbo Boos 4.6 GHz 12MB shared L3 cache. |
| **Memory** | Two user-accessible slots for 8,16,32 or 64 GB of 2666MHz DDR4 SO-DIMM (\*1) | Two user-accessible slots for 8,16,32 or 64 GB of 2666MHz DDR4 SO-DIMM (\*1) |
| **Storage** | 128,256, 512, 1 TB or 2 TB GB PCIe- based SSD | 512, 1 TB or 2 TB GB PCIe- based SSD |
| **Graphics** | Intel UHD Graphics 630 | Intel UHD Graphics 630 |
| **Networking** | 1 x Gigabit Ethernet port 802.11ac Wi-FI wireless networking  IEEE 802.11a/b/g/n compatible  **Optional:**  - 10 Gb Ethernet (optional) | 1 x Gigabit Ethernet port 802.11ac Wi-FI wireless networking  IEEE 802.11a/b/g/n compatible  **Optional:**  - 10 Gb Ethernet (optional) |
| **Connections and Expansion** | Four Thunderbolt 3 (USB-C) port with support for: - DisplayPort - Thunderbolt (up to 40 Gbps) - USB 3.1 Gen 2 (up to 10 Gbps) - Thunderbolt 2, HDMI, DVI and VGA supported  Two USB 3 ports  HDMI 2.0 port  3.5 mm headphone jack | Four Thunderbolt 3 (USB-C) port with support for: - DisplayPort - Thunderbolt (up to 40 Gbps) - USB 3.1 Gen 2 (up to 10 Gbps) - Thunderbolt 2, HDMI, DVI and VGA supported  Two USB 3 ports  HDMI 2.0 port  3.5 mm headphone jack |
| **Dimensions** | 19,7 x 19,7 x 3,6 cm | 19,7 x 19,7 x 3,6 cm |
| **Weight** | 1.3 kg | 1.3 kg |
| **Warranty** | Your Mac mini comes with 90 days of complimentary technical support and a one-year limited warranty. | Your Mac mini comes with 90 days of complimentary technical support and a one-year limited warranty |
| **Remote Management** | No | No |
| **Listed in the VMware Compatibility Guide** | No. So there no official support from VMware. | No. So there no official support from VMware. |
| **Starting price** | € 899 **(\*2)** | € 1.249 **(\*3)** |

**(\*1)** There are two memory slots available.

**(\*2)** The 2018 Mac mini starts at € 899,00 with an i3 processor, 8 GB RAM and 128 GB SSD storage and 1 Gb Ethernet adapter.

**(\*3)** The 2018 Mac mini starts at € 1249,00 with an i5 processor, 8 GB RAM and 256 GB storage and 1 Gb Ethernet adapter.

### Installation of VMware ESXi on the Mac Mini 2018 model

Is it possible to install and run VMware ESXi on the Mac Mini 2018? **Yes with some caveats such as hardware that is not recognized.** The Mac Mini 2018 model is installed with VMware ESXi 6.7 Build 10302608 (ESXi 6.7 U1). Creating a VMware ESXi USB stick is explained in the following blog post, [link](http://localhost/2018/09/16/quick-tip-create-a-bootable-vmware-esxi-key/).

Configuration steps:

- The PCIe-based SSD is not recognized by VMware ESXi. Create an USB key with ESXi installed.
- The Mac Mini 2018 includes a T2 Security Chip, the T2 chip prevents booting booting non legitimate trusted operating systems using secure boot. For ESXi secure boot needs to be disabled. To disable secure boot, boot in the “macOS Utilities”: 
    - Turn on your Mac and press and hold the Command (⌘)-R key immediately after you see the Apple logo

[![](http://localhost/wp-content/uploads/2018/11/IMG-8943-300x194.jpg)](http://localhost/wp-content/uploads/2018/11/IMG-8943.jpg)

[![](http://localhost/wp-content/uploads/2018/11/IMG-8945-300x267.jpg)](http://localhost/wp-content/uploads/2018/11/IMG-8945.jpg)

- Select the “Startup Security Utility” in the Utilities menu.
- Choose “No Security” and select “Allow booting from external media”.
- In the “Startup Security Utility” menu select the Apple icon and select “Shut down”
- Insert the USB drive in one of the USB ports on the back of the Mac Mini 2018
- Press the power button on the back of the Mac Mini and keep the Option (⌥) key pressed for the Startup Manager. Select “EFI Boot” to boot the USB key.

[![](http://localhost/wp-content/uploads/2018/11/IMG-8946-300x225.jpg)](http://localhost/wp-content/uploads/2018/11/IMG-8946.jpg)

- The USB key will start with the ESXi installation.

### Overview

Here is a quick overview of screenshots from ESXi 6.7 U1 on the Mac Mini 2018:

[![](http://localhost/wp-content/uploads/2018/11/esxi-300x140.png)](http://localhost/wp-content/uploads/2018/11/esxi.png) [![](http://localhost/wp-content/uploads/2018/11/esxiputty-300x163.png)](http://localhost/wp-content/uploads/2018/11/esxiputty.png) [![](http://localhost/wp-content/uploads/2018/11/nic-300x46.png)](http://localhost/wp-content/uploads/2018/11/nic.png) [![](http://localhost/wp-content/uploads/2018/11/VM-300x149.png)](http://localhost/wp-content/uploads/2018/11/VM.png)

### Some considerations

- VMware ESXi 6.7 U1 is tested on the Mac Mini 2018 model with a USB stick to boot ESXi. The new Apple Mini 2018 model includes a T2 security chip that use secure boot. Disable secure boot to run VMware ESXi.
- Around 50% CPU and 67% memory load will use around 35 watt.
- The Mac Mini 2018 comes assembled from Apple.
- The CPUs that Apple uses in the Mac Mini 2018 are based on Intel Coffee Lake 8th generation. The CPU is embedded and not upgradeable!
- The new Mac mini allows for memory upgrades up to 64GB on two slots. The memory is it not soldered on the motherboard and is SO-DIMM based. 16 GB cost € 240,00, 32 GB cost € 720,00 and 64 GB cost € 1680,00 extra. To save money go for third-party memory from Kingston or Corsair for example. On iFixit a Mac Mini 2018 memory replacement guide can be found, [link](https://www.ifixit.com/Guide/Mac+mini+Late+2018+Memory+(RAM)+Replacement/115309?fbclid=IwAR2tz8U4_nrhGx6pKLNsGMlThwQC21sTYDpOPxqvl3kUeS-208UMd1ctXis).
- The Apple storage in the Mac mini is PCIe-based and not upgradeable. So size the SSD for the future!
- The PCIe-based SSD is not recognized by VMware ESXi!
- The 1 Gb Ethernet NIC is recognized by ESXi as “Broadcom Corporation NetXtreme BCM57766 Gigabit Ethernet” adapter.
- The 10 GbE NIC is not recognized by VMware ESXi. The NIC is an Aquantia AQC107 and there are no ESXi driver on the moment.
- The Thundebolt controllers are not recognized by ESXi.
- The USB ports are redirected to VMware ESXi.
- A Teardown of the Mac Mini 2018 model can be found here, [link.](https://www.ifixit.com/Teardown/Mac+mini+Late+2018+Teardown/115210)

### Pros &amp; Cons

|  | **Pros** | **Cons** |
|---|---|---|
| **Management** |  | No remote management included |
| **Form factor** | Great looks and form factor |  |
| **Noise level** | Very low |  |
| **Power consumption** | Low. Between ~11w and ~40w with the i3 4-core CPU, 8 GB RAM and 128 GB SSD config and ESXi installed with 1 VM. |  |
| **Memory** | Up to 64 GB (2 memory banks) memory | The memory from Apple is expensive (32 GB will cost € 720,00 and 64 GB will cost € 1680,00 extra). Go for third-party memory memory to save costs. Adding third-party memory means you need to dissemble the Mac Mini! |
| **Upgradeability** | Only the memory can be upgraded. | The CPU and SSD are embedded, soldered and not upgradeable. |
| **Ports** | The USB controller and ports are recognized by ESXi. | The Thunderbolt controllers are not recognized by VMware ESXi. When the Thunderbolt controllers are regornized great Direct Access Storage (DAS) solutions can be build. |
| **Extension** |  | There no room for adding add-on cards and extra disks inside the Mac Mini 2018 box. |
| **Ethernet** | 1 GbE Ethernet NIC is recognized by ESXi | - Only one Ethernet adapter as port available. - The 10 GbE adapter is not recognized by VMware ESXi |
| **VMware ESXi support** | Is tested with ESXi 6.7 U1 when booting from USB key. The 1 GbE NIC is recognized by ESXi. The VM runs from a NAS device over the 1 GbE adapter. | Not on the HCL |
| **Storage** | Use an USB stick to boot ESXi and use remote storage such as a NAS to boot VMs. | The PCIe-based SSD is not recognized by ESXi. |
| **Pricing** |  | For a new homelab host I’ll need at least 32/64 GB memory. When buying the memory from Apple the pricing gets extremely high on the Apple Mac Min 2018. |

### Conclusion

The new Mac Mini 2018 hardware specifications are a great refreshment compared to the old Mac Mini 2012 model, but it comes with a very high price for the most homelabers. The PCIe-based SSD, 10 Gb Ethernet adapter and Thunderbolt controllers are not (yet) recognized by VMware ESXi. I think there are better homelab options available on the moment for less money.
