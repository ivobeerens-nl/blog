---
author: Ivo Beerens
categories:
- ESXi
- vsphere5
date: "2011-08-18T16:52:56Z"
guid: http://www.ivobeerens.nl/?p=979
id: 979
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- esxi
- vsphere5
title: Upgrading to VMware ESXi 5
url: /2011/08/18/upgrading-to-vmware-esxi-5/
---

<font color="#000000"></font>

<font color="#000000">The following three supported upgrade methods to VMware ESXi 5 are available:</font>

| **<font color="#000000">Upgrade Method</font>** | **<font color="#000000">ESX or ESXi to ESXi 5</font>** | **<font color="#000000">Upgrade or Patch from ESXi 5.0 to    ESXi 5.n</font>** |
|---|---|---|
| **<font color="#000000">vSphere Update Manager</font>** | <font color="#000000">yes</font> | <font color="#000000">yes</font> |
| **<font color="#000000">Interactive upgrade from CD, DVD, or    USB drive</font>** | <font color="#000000">yes</font> | <font color="#000000">yes</font> |
| **<font color="#000000">Scripted upgrade</font>** | <font color="#000000">yes</font> | <font color="#000000">yes</font> |
| **<font color="#000000">vSphere Auto Deploy</font>** | <font color="#000000">no</font> | <font color="#000000">yes</font> |
| **<font color="#000000">esxcli</font>** | <font color="#000000">no</font> | <font color="#000000">yes</font> |

<font color="#000000"></font>

<font color="#000000">It is not supported to directly upgrade ESX(i) 3.x to ESXi 5. You must first upgrade ESX(i) 3 to ESX(i) 4 before upgrading to ESXi 5. Another option is to do an fresh installation.</font>

<font color="#000000">**When upgrading to vSphere ESXi 5 there are a couple of things to think about before starting**:</font>

<font color="#000000">– It is now possible to upgrade VMware ESX 4.x and ESXi 4.x to VMware ESXi 5. Prior ESXi 5 the upgrade from ESX to ESXi was not supported (fresh installation needed).</font>

<font color="#000000">– Make sure using static IP addresses. DHCP addresses can cause problems when upgrading with VMware Update Manager </font>

<font color="#000000">– Backup your ESX or ESXi configuration:</font>

> <font color="#000000">For ESX back up the /etc/passwd, /etc/groups, /etc/shadow, and /etc/gshadow directories, custom scripts, local VMs, templates, iso and \*.VMX files</font>

> <font color="#000000">For ESXi use vicfg-cfgbackup command in from the VMA or esxcli</font>

<font color="#000000">– If upgrading the host(s) managed by vCenter server, you must upgrade vCenter to version 5 before upgrade ESX or ESXi</font>

<font color="#000000">– Once you have upgraded or migrated your host to ESXi 5.0, you cannot roll back to your   
version 4.x ESX or ESXi software.</font>

<font color="#000000">– Lopsided boot banks can occur in systems that are upgraded from ESXi 3.5 to ESXi 4.x, and then upgraded directly to ESXi 5.0. vSphere Update Manager assumes the boot banks are both at 250MB. If it detects one boot bank is smaller than the other it will report an invalid boot disk and won’t even try to upgrade. More information can be found </font>[<font color="#000000">here</font>](http://blogs.vmware.com/esxi/2011/08/esxi-and-lopsided-bootbanks.html)<font color="#000000">.</font>

<font color="#000000">– For most ESXi 4.x hosts, the partition table is not rewritten in the upgrade to ESXi 5.0. The partition table is rewritten for systems that have lopsided bootbanks. Lopsided boot banks can occur in systems that are upgraded from ESXi 3.5 to ESXi 4.x, and then directly to ESXi 5.0.</font>

<font color="#000000">– The ESXi 5.0 installer cannot detect ESX 2.x instances or VMFS2 datastores. You cannot migrate ESX 2.x instances to ESXi 5.0 or preserve VMFS2 datastores in an upgrade to ESXi 5.0. Instead, perform a fresh installation of ESXi 5.0.</font>

<font color="#000000">– For ESX hosts, the partitioning structure is changed to resemble that of an ESXi 4.x host. The VMFS3 partition is retained and a new MSDOS-based partition table overwrites the existing partition table.</font>

<font color="#000000">– Upgraded hosts do not have a scratch partition. Instead, the scratch directory is created and accessed off of the VMFS volume. Each of the other partitions, such as the bootbanks, locker and vmkcore will be identical to thatof any other system.</font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000">**The three upgrade methods are described with some screenshots.**</font>

### <font color="#000000">vSphere Update Manager (VUM) ESX 4 or ESXi 4 to ESXi 5 upgrade</font>

<font color="#000000">In vCenter open the VUM plug in and import Host Upgrade Image</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb9.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image9.png)

<font color="#000000">browse to the VMware vSphere 5i installer ISO</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb10.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image10.png)

<font color="#000000">The ISO is uploaded to VUM. </font>

[<font color="#000000">![2011-08-19 10h37_31](http://localhost/wp-content/uploads/2011/08/2011-08-19-10h37_31_thumb.jpg "2011-08-19 10h37_31")</font>](http://localhost/wp-content/uploads/2011/08/2011-08-19-10h37_31.jpg)

<font color="#000000">Create Host Upgrade Baseline</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb11.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image11.png)

<font color="#000000">Attach the baseline</font>

[<font color="#000000">![2011-08-19 10h40_12](http://localhost/wp-content/uploads/2011/08/2011-08-19-10h40_12_thumb.jpg "2011-08-19 10h40_12")</font>](http://localhost/wp-content/uploads/2011/08/2011-08-19-10h40_12.jpg)

<font color="#000000">Perform an scan</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb12.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image12.png)

<font color="#000000">There is a warning. Click on the 1 to expand the warning</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb13.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image13.png)

<font color="#000000">The following warning is displayed that some modules are removed by the upgrade</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb14.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image14.png)

<font color="#000000">Click on the Remediate button and follow the steps:</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb15.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image15.png)

[<font color="#000000">![2011-08-19 11h00_15](http://localhost/wp-content/uploads/2011/08/2011-08-19-11h00_15_thumb.jpg "2011-08-19 11h00_15")</font>](http://localhost/wp-content/uploads/2011/08/2011-08-19-11h00_15.jpg)

[<font color="#000000">![2011-08-19 11h01_40](http://localhost/wp-content/uploads/2011/08/2011-08-19-11h01_40_thumb.jpg "2011-08-19 11h01_40")</font>](http://localhost/wp-content/uploads/2011/08/2011-08-19-11h01_40.jpg)

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb16.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image16.png)

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb17.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image17.png)

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb18.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image18.png)

<font color="#000000"></font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb19.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image19.png)

<font color="#000000">When the Remediate finish the upgrade is complete and VMware ESXi 5 is installed.</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb20.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image20.png)

<font color="#000000"></font>

### <font color="#000000">Steps of the interactive upgrade using the CD/DVD from ESX4 or ESXi 4 to ESXi 5</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb2.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image2.png)

<font color="#000000"></font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb3.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image3.png)

<font color="#000000"></font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb4.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image4.png)

<font color="#000000"></font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb5.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image5.png)

A existing VMFS volume is found and the following selections can be made:

<font color="#000000"></font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb6.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image6.png)

<font color="#000000">In this example we migrate VMware ESX 4 to ESXi 5 and choose Migrate ESX, preserver VMFS datastore.</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb7.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image7.png)

<font color="#000000"></font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/08/image_thumb8.png "image")</font>](http://localhost/wp-content/uploads/2011/08/image8.png)

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

### <font color="#000000">Scripted upgrade from ESX4 or ESXi 4 to ESXi 5</font>

<font color="#000000">Scripted upgrade can be done by using a kickstart text file for example ks.cfg. In this file the following options can be used for the upgrade:</font>

| **<font color="#000000">upgrade</font>** | <font color="#000000">Upgrades to ESXi 5</font> |
|---|---|
| <font color="#000000">**installorupgrade**</font> | <font color="#000000">Tries to upgrade to ESXi5. If it is not possible to upgrade it will perform a fresh installation.</font> |

<font color="#000000">William Lam has very good information and examples about ESXi 5 scripted installations. For more information see the posts </font><font color="#000000">[How to Automate the Upgrade of Classic ESX 4.x to ESXi 5](http://www.virtuallyghetto.com/2011/08/how-to-automate-upgrade-of-classic-esx.html) and [Automating ESXi 5.x Kickstart Tips &amp; Tricks](http://www.virtuallyghetto.com/2011/07/automating-esxi-5x-kickstart-tips.html) </font>

\[ad#banner\]
