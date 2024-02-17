---
author: Ivo Beerens
categories:
- licensing
- vpshere
- vpshere 5
date: "2011-07-15T14:25:53Z"
guid: http://www.ivobeerens.nl/?p=935
id: 935
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- licensing
- vSphere
- vsphere5
title: VMware vSphere 5 licensing update explained
url: /2011/07/15/vmware-vsphere-5-licensing-explained/
---

<span style="color: #000000;">With the announcement of VMware vSphere 5 a complete new license model is introduces.</span>

<span style="color: #000000;">In VMware vSphere 4 the licensing model was per physical processor based on the number of cores per CPU and the physical memory.</span>

<span style="color: #000000;">The VMware vSphere 5 license model is based per physical processor and the **allocated** memory (vRAM) across the entire vSphere environment for a particular vSphere 5 edition (pool).</span>

<span style="color: #000000;">VMware has released a [video](http://download3.vmware.com/media/vsphere/licensing/vs5_licensing_pricing.html) which explains the new vSphere 5 licensing model.</span>

<span style="color: #ff0000;">**<u>Update August 27, 2012</u>**</span>

<span>**<span style="color: #ff0000;">Today VMware announced the end of the vRAM entitlement. More info can be found </span>[here](http://localhost/2012/08/27/the-end-of-the-vram-entitlement-in-vmware-vsphere-5-and-5-1/)<span style="color: #ff0000;">.</span>**</span>

<span style="color: #ff0000;">**<u>Update August 15, 2011</u>**</span>

**<span style="color: #000000;">VMware has announced an update in the licensing for vSphere 5. They listens to their customers and changed the licensing. </span><span style="color: #000000;">The following things have been updated:</span>**

**<span style="color: #000000;">– The vRAM entitlements are increased. See the new entitlements in this post.</span>**

**<span style="color: #000000;">– Capped amount of vRAM that is counted for a VM with a max of 1 vSphere Enterprise license (96GB). So an 1TB VM cost 96GB.</span>**

**<span style="color: #000000;">– More flexible around transient workloads, and short-term spikes that are typical in test &amp; development environments for example. We will now calculate a 12-month average of consumed vRAM to rather than tracking the high water mark of vRAM.</span>**

<span style="color: #000000;">**–** </span><span style="color: #000000;">**VMware launched an official tool “The VMware vSphere Licensing Advisor”. This tool allows users with vSphere 4.1, vSphere 4.0 and Virtual Infrastructure 3.5 environments to calculate and understand their vRAM usage and vRAM capacity as if they upgraded to vSphere 5.0.**</span>

**<span style="color: #ff0000;">Everything in red colored text is updated.</span>**

<span style="color: #000000;">**vSphere 5 licensing facts:**</span>

<span style="color: #000000;">– vRAM = virtual memory configured to a Virtual Machine</span>

<span style="color: #000000;">– Pooled vRAM = sum of all vRAM entitlements across all vSphere 5 licenses from the same edition in one or more vCenter(s) servers in linked mode </span>

<span style="color: #000000;">– Only powered-on VMs a counted in the total vRAM.</span>

<span style="color: #000000;">– vRAM pool must be licensed with the same vSphere edition. </span>

<span style="color: #000000;">– You can multiple vRAM pools in one or more vCenter servers for example a vSphere 5 standard and vSphere 5 Enterprise license pool</span>

<span style="color: #000000;">– The vSphere 4 Advanced edition is removed and customers get a free upgrade to Enterprise</span>

#### vSphere editions and vRAM entitlement

<span style="color: #000000;">The following vSphere 5 editions are available:</span>

| **<span style="color: #000000;">vSphere 5 edition</span>** | **<span style="color: #000000;">Old vRAM (GB) entitlement per Physical CPU </span>** | **<span style="color: #000000;"><span style="color: #ff0000;">NEW vRAM (GB) entitlement per Physical CPU</span> </span>** | **<span style="color: #000000;">Max vCPU/VM</span>** |
|---|---|---|---|
| <span style="color: #000000;">vSphere 5 Hypervisor (free version)</span> | <span style="color: #000000;">8</span> | <span style="color: #ff0000;">32 Physical limit (no vRAM entitlement)</span> | <span style="color: #000000;">8</span> |
| <span style="color: #000000;">vSphere 5 Essentials</span> | <span style="color: #000000;">24 (max. 6 processor license, total <span style="color: #ff0000;">192GB</span>)</span> | <span style="color: #ff0000;">32</span> | <span style="color: #000000;">8</span> |
| <span style="color: #000000;">vSphere 5 Essentials plus</span> | <span style="color: #000000;">24 (max. 6 processor license, total <span style="color: #ff0000;">192GB</span>)</span> | <span style="color: #ff0000;">32</span> | <span style="color: #000000;">8</span> |
| <span style="color: #000000;">vSphere 5 Standard</span> | <span style="color: #000000;">24</span> | <span style="color: #ff0000;">32</span> | <span style="color: #000000;">8</span> |
| <span style="color: #000000;">vSphere 5 Enterprise</span> | <span style="color: #000000;">32</span> | <span style="color: #ff0000;">64</span> | <span style="color: #000000;">8</span> |
| <span style="color: #000000;">vSphere 5 Enterprise plus</span> | <span style="color: #000000;">48</span> | <span style="color: #ff0000;">96</span> | <span style="color: #000000;">32</span> |

#### How many licenses do I need?

<span style="color: #000000;">For existing customers before upgrading to vSphere 5 you need to know if the upgrade can without needing extra licenses. </span>

<span style="color: #000000;">To calculate how many licenses you need to sum up the total amount of vRAM allocated in all the powered-on VMs and divide that to total amount by the for the particular vSphere 5 edition you are running. Here are two customer cases: </span>

**<span style="color: #000000;">Customer example 1</span>**

<span style="color: #000000;">Stretched cluster across two sites. One VMware vCenter server and 19 VMware vSphere 4 hosts. 2 Clusters. </span>

| **<span style="color: #000000;">Cluster</span>** | **<span style="color: #000000;">vSphere 4 hosts</span>** | **<span style="color: #000000;">License</span>** |
|---|---|---|
| <span style="color: #000000;">Cluster Citrix</span> | <span style="color: #000000;">10</span> | <span style="color: #000000;">Standard</span> |
| <span style="color: #000000;">Cluster HA&amp;DRS</span> | <span style="color: #000000;">9</span> | <span style="color: #000000;">Enterprise</span> |

<span style="color: #000000;">vSphere host hardware:</span>

<span style="color: #000000;">– HP Proliant DL 380 G6</span>

<span style="color: #000000;">– 2 x Intel Xeon 5500 CPUs</span>

<span style="color: #000000;">– 48 GB memory</span>

| <span style="color: #000000;">VMware vSphere hosts</span> | <span style="color: #000000;">19</span> |
|---|---|
| <span style="color: #000000;">License type</span> | <span style="color: #000000;">vSphere 4 Enterprise (9)   vSphere 4 standard (10)</span> |
| <span style="color: #000000;">Total CPU licenses</span> | <span style="color: #000000;">vSphere 4 Enterprise 18   vSphere 4 standard 20</span> |
| <span style="color: #000000;">Max pooled vRAM</span> | <span style="color: #000000;">vSphere Enterprise gives per CPU <span style="color: #ff0000;">64GB</span>, 18 x <span style="color: #ff0000;">64GB</span> = <span style="color: #ff0000;">1152GB</span> Pooled vRAM vSphere Standard gives per <span style="color: #ff0000;">CPU 32GB</span>, 20 x 32GB = <span style="color: #ff0000;">640 GB</span> Pooled vRAM  </span> |
| <span style="color: #000000;">Current vRAM usage</span> | <span style="color: #000000;">312 GB Enterprise pool   320 GB Standard pool</span> |
| <span style="color: #000000;">Maximum usage RAM (100% use)</span> | <span style="color: #000000;">432 GB (9 x 48GB) Enterprise   480 GB (10 x 48GB) Standard</span> |

<span style="color: #000000;">No additional licenses will be required for this environment.</span>

**<span style="color: #000000;">Customer example 2</span>**

<span style="color: #000000;">Two sites, on every site one vCenter server and 4 VMware vSphere 4 hosts with VMware Site Recovery Manager (SRM).</span>

<span style="color: #000000;">vSphere host hardware:</span>

<span style="color: #000000;">– HP Proliant DL 380 G7</span>

<span style="color: #000000;">– 2 x Intel Xeon 5650 CPUs</span>

<span style="color: #000000;">– 72 GB memory</span>

<span style="color: #000000;">**Site 1**</span>

| <span style="color: #000000;">VMware vSphere hosts</span> | <span style="color: #000000;">4</span> |
|---|---|
| <span style="color: #000000;">License type</span> | <span style="color: #000000;">vSphere 4 Enterprise</span> |
| <span style="color: #000000;">Total licenses</span> | <span style="color: #000000;">8</span> |
| <span style="color: #000000;">Max pooled vRAM</span> | <span style="color: #000000;">vSphere enterprise gives per CPU <span style="color: #ff0000;">64GB</span>, 8 x <span style="color: #ff0000;">64GB</span> = <span style="color: #ff0000;">512GB</span> Pooled vRAM</span> |
| <span style="color: #000000;">Current vRAM usage</span> | <span style="color: #000000;">177 GB</span> |
| <span style="color: #000000;">Maximum usage RAM (100% use)</span> | <span style="color: #000000;">288 GB (4 x 72GB)</span> |

<span style="color: #000000;">**Site 2**</span>

| <span style="color: #000000;">VMware vSphere hosts</span> | <span style="color: #000000;">4</span> |
|---|---|
| <span style="color: #000000;">License type</span> | <span style="color: #000000;">vSphere 4 Enterprise</span> |
| <span style="color: #000000;">Total licenses</span> | <span style="color: #000000;">8</span> |
| <span style="color: #000000;">Max pooled vRAM</span> | <span style="color: #000000;">vSphere enterprise gives per CPU <span style="color: #ff0000;">64GB</span>, 8 x <span style="color: #ff0000;">64GB</span> = <span style="color: #ff0000;">512GB</span> Pooled vRAM</span> |
| <span style="color: #000000;">Current vRAM usage</span> | <span style="color: #000000;">68 GB</span> |
| <span style="color: #000000;">Maximum usage RAM (100% use)</span> | <span style="color: #000000;">288 GB (4 x 72GB)</span> |

<span style="color: #000000;">No additional licenses will be required for this environment </span><span style="color: #ff0000;"><span style="text-decoration: line-through;">even if the 288 GB RAM cannot be full used. This because of the reservation of an X amount of memory in your cluster for the hypervisor, maintenance mode and High Availability (HA)</span>.</span>

#### Cons of the new vSphere 5 licensing

<span style="color: #000000;">VMware listening to there customers and increased for example the vRAM entitlements. To most of the cons do not apply anymore. </span>

<span style="color: #000000;"><span style="text-decoration: line-through;">– Customers are or going to upgrade to Microsoft Windows 2008 R2. Our Windows 2008 R2 templates are based 4GB of more depending on the task the VM gets. As we take 4GB as average the following 4GB VMs can be placed with 100% memory use:</span></span>

| **<span style="color: #000000;"><span style="text-decoration: line-through;">vSphere 5 edition</span></span>** | **<span style="color: #000000;"><span style="text-decoration: line-through;">vRAM (GB) entitlement per Physical CPU </span></span>** | **<span style="color: #000000;"><span style="text-decoration: line-through;">Windows 2008 R2 VMs</span></span>** |
|---|---|---|
| <span style="color: #000000;"><span style="text-decoration: line-through;">vSphere 5 Hypervisor (free version)</span></span> | <span style="color: #ff0000;"><span style="text-decoration: line-through;">8   </span>32 physical limit</span> | <span style="color: #ff0000;">2   8</span> |
| <span style="color: #000000;"><span style="text-decoration: line-through;">vSphere 5 Essentials</span></span> | <span style="color: #ff0000;"><span style="text-decoration: line-through;">24 (max. 6 processor license, total 144GB)   </span>32</span> | <span style="color: #ff0000;">6 8  </span> |
| <span style="color: #000000;"><span style="text-decoration: line-through;">vSphere 5 Essentials plus</span></span> | <span style="color: #ff0000;"><span style="text-decoration: line-through;">24 (max. 6 processor license, total 144 GB)   </span>32</span> | <span style="color: #ff0000;"><span style="text-decoration: line-through;">6   </span>   8</span> |
| <span style="color: #000000;"><span style="text-decoration: line-through;">vSphere 5 Standard</span></span> | <span style="color: #ff0000;"><span style="text-decoration: line-through;">24   </span>32 </span> | <span style="color: #ff0000;"><span style="text-decoration: line-through;">6   </span>8</span> |
| <span style="color: #000000;"><span style="text-decoration: line-through;">vSphere 5 Enterprise</span></span> | <span style="color: #ff0000;"><span style="text-decoration: line-through;">32   </span>64</span> | <span style="color: #ff0000;"><span style="text-decoration: line-through;">8   </span>16</span> |
| <span style="color: #000000;"><span style="text-decoration: line-through;">vSphere 5 Enterprise plus</span></span> | <span style="color: #ff0000;"><span style="text-decoration: line-through;">48   </span>96</span> | <span style="color: #ff0000;"><span style="text-decoration: line-through;">12   </span>24</span> |

<span style="color: #000000;"><span style="text-decoration: line-through;">– The CPU core to memory ratio can be very low. For example for a six core CPU with hyper-treading and a standard license gives a very low ratio 1:1 if we use 4GB VMs. </span></span>

<span style="text-decoration: line-through;"><span style="color: #000000;">– You may loss the the flexibility to scale-up the memory without invest in extra vSphere licenses. I have seen a lot of customers who upgrade the memory of their vSphere hosts within 3 a 4 years. With the new vSphere 5 licensing this can lead in buying extra licenses.</span> </span>

<span style="color: #000000;"><span style="text-decoration: line-through;">– The vSphere 5 Hypervisor version supports 8GB per CPU, a dual CPU sockets hosts gives u 16GB RAM. On this server you can place 3,5 Windows 2008 R2 VM with 4GB VMs. I think the vSphere 5 Hypervisor isn’t going to be used anymore because other hypervisors haven’t this restriction and even offer more functionality.</span></span>

<span style="color: #000000;"><span style="text-decoration: line-through;">– No benefit for memory technics such as memory over allocation because the licensing is based on virtual memory configured to a Virtual Machine (vRAM)</span> </span>

#### Tools

<span style="color: #000000;">Before upgrading to vSphere 5 you need to know if the upgrade can without needing extra licenses. </span><span style="color: #000000;">Here’s are some great PowerCLI script the examine the vRAM usage and licenses used in your current vSphere environment:</span>

<span style="color: #000000;">– [vSphere Licensing Advisor](http://downloads.vmware.com/d/details/licenseadv10/ZHcqYnQldHdiZCpwcA==). </span><span style="color: #ff0000;">The VMware vSphere Licensing Advisor allows users with vSphere 4.1, vSphere 4.0 and Virtual Infrastructure 3.5 environments to calculate and understand their vRAM usage and vRAM capacity as if they upgraded to vSphere 5.0. The tool will show you the vRAM capacity and usage for each vSphere 5.0 equivalent edition.</span>

[![image](http://localhost/wp-content/uploads/2011/08/image_thumb.png "image")](http://localhost/wp-content/uploads/2011/08/image.png)

– [License Validator](http://www.virtu-al.net/2011/07/14/vsphere-5-license-entitlements/) by Alan Renouf

– [Query vRAM](http://www.lucd.info/2011/07/13/query-vram/) by Luc Dekens

– Calculate vSphere 5 licenses by Hugo Peeters

<span style="color: #000000;">Other stuff:</span>

– [VMware vSphere 5.0 Licensing, Pricing and Packaging whitepaper](http://www.vmware.com/files/pdf/vsphere_pricing.pdf)

– [Virtual License Calculator by Rynard Spies](http://www.virtualvcp.com/news/165-my-vmware-vsphere-5-license-calculator-published)

<span style="color: #000000;">VMware has a white paper about the vSphere 5 new licensing structure and can be found [here](http://www.vmware.com/files/pdf/vsphere_pricing.pdf)</span><span style="color: #000000;">. There is also a vSphere 5 licensing discussion on the [VMware Community](http://communities.vmware.com/thread/320877?start=0&tstart=0).</span>

#### VDI licenses

<span style="color: #000000;">For VDI desktops VMware a “vSphere Desktop” package license is introduces. This license is a lot easier to understand. For a 100 concurrent desktop license you pay $6500, that is $65 per desktop regardless the processors, memory you have.</span>
