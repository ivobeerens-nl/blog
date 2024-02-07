---
author: Ivo Beerens
categories:
- Home Lab
- vSphere
- Whitebox
date: "2011-11-18T11:27:43Z"
guid: http://www.ivobeerens.nl/2011/11/18/time-for-new-whitebox-for-your-vmware-vsphere-or-ms-hyper-v-home-lab-environment/
id: 1152
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- vSphere
- Whitebox
title: Time for new whitebox for your VMware vSphere or MS Hyper-V home lab environment?
url: /2011/11/18/time-for-new-whitebox-for-your-vmware-vsphere-or-ms-hyper-v-home-lab-environment/
---

<span style="color: #000000;">When using a whitebox lab environment at home and like to test for example vSphere 5, vCloud Director, VMware View and MS Hyper-V (nested in VMware vSphere ![Glimlach](http://localhost/wp-content/uploads/2011/11/wlEmoticon-smile.png)) you need a lot of processor power and memory. In almost all whitebox lab environment the processor power is not the problem but the amount of memory is.</span>

<span style="color: #000000;">Till now the Sandy Bridge desktop boards support up to 32GB memory with only four DIMM slots on the motherboard. For 32GB you need 4 \* 8GB DIMMs, 8GB DIMMs are very expensive on the moment when writing this post.</span>

<span style="color: #000000;">Intel Introduced the Sandy Bridge-E processors and motherboards with the X79 based chipset that support this processors. This gives new possibilities for building a new whitebox home lab.</span>

### <span style="color: #000000;">Processor</span>

<span style="color: #000000;">Intel introduced the Sandy Bridge-E or the 2nd generation Core i7 Extreme Processors. On the moment there are two Sandy Bridge-E processors available:</span>

<span style="color: #000000;">– Intel Core-I7-3960X 3,3GHz,15M L3-cache, list price around <span style="color: #000000;"><span style="font-size: small;">€</span></span>950,00</span>

<span style="color: #000000;">– Intel Core-I7-3930K 3,2GHz,12M L3-cache, list price around <span style="color: #000000;"><span style="font-size: small;">€ </span></span>550,00</span>

<span style="color: #000000;">As you can see the processors are pretty expensive. The Sandy Bridge-E has the following features:</span>

<span style="color: #000000;">– Socket LGA2011;</span>

<span style="color: #000000;">– 6 cores (12 cores with Hyper-Threading);</span>

<span style="color: #000000;">– Quad channel DDR3-1600 memory controller; </span>

<span style="color: #000000;">– Supports Hyper-Threading, Intel VT-x, VT-d;</span>

<span style="color: #000000;">– PCI-Express 3.0 support;</span>

<span style="color: #000000;">– 40 PCI-Express lanes;</span>

<span style="color: #000000;">– Max TDP 130 W;</span>

<span style="color: #000000;">– Multiplier unlocked.</span>

<span style="color: #000000;">The 2nd generation Core i7 Extreme Processors can be compared</span> [here](http://ark.intel.com/).

<span style="color: #000000;">Begin 2012 Intel will release the **Core I7 3820** Sandy Bridge-E processor. This processor will support **4 cores** (8 with Hyper-Threading) and have **10MB** L3-cache. The price is not announced yet but will be much lower as the Intel 3930K and 3960X processors. When you buy a Sandy Bridge-E processor there is no CPU cooler in the box.</span>

### Motherboard

<span style="color: #000000;">The Intel X79 chipset support the Socket LGA2011. To choose a motherboard you can for example check the following things: </span>

<span style="color: #000000;">– How much DIMM slots it has (some X79 motherboard have 4 DIMM slots);</span>

<span style="color: #000000;">– How much expansion slots it has;</span>

<span style="color: #000000;">– Price;</span>

<span style="color: #000000;">– How many USB ports and what speed they have;</span>

<span style="color: #000000;">– Type and number of SATA controllers;</span>

<span style="color: #000000;">– Type of number of NIC(s).</span>

<span style="color: #000000;">Important for a whitebox lab configuration is that the SATA controller (if you want to use local storage) and NIC(s) are supported by VMware ESXi. When choosing a motherboard with enough expansion slots you can always add extra RAID and NIC cards that are supported.</span>

<span style="color: #000000;">The most X79 based motherboards have 8 DIMM slots and supports up to 64GB memory. 8GB memory modules are expensive. So you can make a configuration with 8 x 4GB = 32 GB DDR-3 memory which is much cheaper. When 8GB memory modules become cheaper you can upgrade to 64GB memory.</span>

<span style="color: #000000;">Asus has a nice overview of all the X79 bases series motherboards they have, found</span> here.

### Shopping list

<span style="color: #000000;">I made a shopping without the case, storage and the power supply. The prices are taken from the </span>[<span style="color: #000000;">Tweakers pricewatch</span>](http://tweakers.net/pricewatch/) <span style="color: #000000;">(Dutch)</span><span style="color: #000000;"> an can change every day.</span>

<span style="color: #000000;">**Shopping list**:</span>

| **<span style="color: #000000;">Component</span>** | <span style="color: #000000;">**List price (**<span style="font-size: small;">€ </span>**)**</span> |
|---|---|
| <span style="color: #000000;">Intel Core-I7-3930K</span> | <span style="color: #000000;">520,00</span> |
| <span style="color: #000000;">Asus P9X79</span> | <span style="color: #000000;">230,00</span> |
| <span style="color: #000000;">4 x 4 x 2GB DDR3-1600 memory (total 32GB)</span> | <span style="color: #000000;">160,00</span> |
| <span style="color: #000000;">Simple processor cooler</span> | <span style="color: #000000;">30,00</span> |
| <span style="color: #000000;">Simple graphic card PCI-E</span> | <span style="color: #000000;">25,00</span> |
| **<span style="color: #000000;">Total</span>** | <span style="color: #000000;">**965,00** <span style="font-size: small;"> </span> </span> |

### Conclusion

<span style="color: #000000;">With the Sandy Bridge-E processor and X79 based motherboard you can build a monster whitebox lab environment with the best performance on the moment.</span>

<span style="color: #000000;">The advantage of using one huge whitebox you can use nesting to run your VMware vSphere and MS Hyper-V environment(s) on one box. An other advantage of using a whitebox is that you can make a low noise system. It’s a lot of money for a whitebox home lab environment but if you </span><span style="color: #000000;">you wait for the Intel **Core I7 3820** Sandy Bridge-E processor (announced in January 2012) can save you around <span style="font-size: small;">€</span>270,00 (this is an assumption because the list prices are not available yet).</span>

\[ad#banner\]
