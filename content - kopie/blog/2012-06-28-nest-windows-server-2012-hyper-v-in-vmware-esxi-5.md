---
author: Ivo Beerens
categories:
- ESXi
- Hyper-V
- windows server 2012
date: "2012-06-28T11:57:07Z"
guid: http://www.ivobeerens.nl/?p=1606
id: 1606
ssb_fbshare_counts:
- "6"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:6;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "6"
tags:
- esxi
- hyper-v
- windows server 2012
title: Nest Windows Server 2012 Hyper-V in VMware ESXi 5
url: /2012/06/28/nest-windows-server-2012-hyper-v-in-vmware-esxi-5/
---

In this blog post I explain how you can install Windows 2012 Server Release Candidate (RC) in VMware ESXi and enable the Hyper-V role. It is possible to build a Hyper-V cluster LAB and live migrate VMs between the virtual Hyper-V nodes on one VMware ESXi 5 host.

Before you begin make sure:

- Windows 2012 Server RC ISO is place on a datastore
- VMware ESXi 5 Update 1 is installed with the latest updates
- To be able to boot 64bit guest OSes, make sure that on the VMware ESXi host the line below is added to the **/etc/vmware/config** file on your physical ESXi 5.x host (more information can be found on the blog from [William Lam](http://www.virtuallyghetto.com/2011/07/how-to-enable-support-for-nested-64bit.html))

```
<pre lang="plain">vhv.allow = TRUE
```

Create a new VM with the following settings (adjust the settings for your own need):

- Configuration – **Custom**
- Name – **HV2012-02**
- Storage – Choose **VMFS**
- Virtual Machine Version – **Virtual Machine Version 8**
- Guest Operating System – **Microsoft Windows Server 2008 R2 (64-bit)**
- CPUs – **2 Sockets, 2 Cores**
- Memory – **4 GB**
- Network – **4 NICs VMXNET 3**
- SCSI Controller – **LSI logic SAS**
- Create a new virtual disk
- Disk Size – **40 GB**
- Virtual Device Node – **SCSI(0:0)**
- **Finish**

After the VM is created edit the VM configuration and add or change the following settings:

- Hardware – CD/DVD drive 1 – Datastore ISO file – browse to the Windows Server 2012 ISO
- Options – General Options – Guest Operating System – **Microsoft Windows Server 8 (64-bit**)
- Options – CPUID Mask – Advanced – Level 1 ecx (**add the mask below for Intel Hosts**)

```
<pre lang="plain">---- ---- ---- ---- ---- ---- --H- ----
```

- Options – Boot Options – Specify the boot firmware – **EFI**

| [![image](http://localhost/wp-content/uploads/2012/06/image_thumb6.png "image")](http://localhost/wp-content/uploads/2012/06/image6.png) | [![image](http://localhost/wp-content/uploads/2012/06/image_thumb7.png "image")](http://localhost/wp-content/uploads/2012/06/image7.png) |
|---|---|
| [![image](http://localhost/wp-content/uploads/2012/06/image4_thumb.png "image")](http://localhost/wp-content/uploads/2012/06/image41.png) | [![image](http://localhost/wp-content/uploads/2012/06/image_thumb9.png "image")](http://localhost/wp-content/uploads/2012/06/image9.png) |

- Options – General – Configuration Parameters – Add Row – Add the line below (without =)

```
<pre lang="plain">hypervisor.cpuid.v0 = FALSE 
```

- Start the VM and install Windows Server 2012
- Install VMware tools
- Add the Hyper-V role

If you need to install more Windows Server 2012 Hyper-V VMs, create a template so that you only need to do the settings once.

[![image](http://localhost/wp-content/uploads/2012/06/image_thumb8.png "image")](http://localhost/wp-content/uploads/2012/06/image8.png)
