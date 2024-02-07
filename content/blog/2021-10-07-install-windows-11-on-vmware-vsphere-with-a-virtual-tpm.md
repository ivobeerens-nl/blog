---
author: Ivo Beerens
categories:
- Windows 11
date: "2021-10-07T22:36:33Z"
guid: https://www.ivobeerens.nl/?p=8078
id: 8078
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- TPM
- VMware
- Windows 11
title: Install Windows 11 on VMware vSphere with a virtual TPM
url: /2021/10/07/install-windows-11-on-vmware-vsphere-with-a-virtual-tpm/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

Yesterday I wrote a blog called “[Install Windows 11 as VM on VMware vSphere / Workstation without TPM 2.0 chipset](http://localhost/2021/10/06/install-windows-11-as-vm-in-vmware-vsphere-workstation-without-tpm-2-0/)“. In this blog article, I explained how to install Windows 11 without having a TPM 2.0 chipset by using a registry hack. Paul Braren from tinkertry.com created a cool video ([link](https://www.youtube.com/watch?v=wh-KoJKtm2k)) about installing Windows 11 on VMware vSphere using my blog article. Bob Plankers (<span class="css-901oao css-16my406 r-poiln3 r-bcqeeo r-qvutc0">@plankers) replied on Twitter that virtual TPM can be used too. </span>

> You can just add a virtual TPM in Workstation or vSphere, too.
> 
> — (@plankers) [October 6, 2021](https://twitter.com/plankers/status/1445789003761004546?ref_src=twsrc%5Etfw)

So I did some research in my home lab. With VMware vSphere and VMware Workstation, it is possible to install Windows 11 by using a vTPM device that emulates a physical TPM 2.0 chipset without having one. This is called Virtual Trusted Platform Module (vTPM). A vTPM performs the same functions as a hardware TPM, it performs cryptographic coprocessor capabilities in software So without having a physical TPM 2.0 you can run Windows 11 without performing any hacks to the Windows 11 Operating System.

In this blog post, I explain how to configure vTPM for VMware vSphere and install Windows 11. Here are the steps:

### **Requirements for vTPM**

- EFI firmware
- Hardware Version 14 or later
- vSphere 6.7 or later
- Virtual Machine encryption
- Key Provider. The Key Provider is used to enable encrypted technologies such as TPM

### To enable vTPM you must first add a Key Provider

- Open the vSphere Client URL (**https://vcentername/ui**)
- Log-in
- Click on the vCenter name – **Configure** and select **Key Providers**
- Click on **ADD**
- Select **Add Native Key Provider.** When using the Native Key provider you don’t need an external key server**.**
- Enter a name for the Key Provider and **uncheck** “Use key provider only with TPM protected ESXi hosts (Recommended).

[![](http://localhost/wp-content/uploads/2021/10/1-1-300x143.jpg)](http://localhost/wp-content/uploads/2021/10/1-1.jpg)

- Select **Backup** and uncheck “**Protect Native Key Provider data with password (Recommended)**” and click on **BACK UP KEY PROVIDER**

[![](http://localhost/wp-content/uploads/2021/10/2-1-300x199.jpg)](http://localhost/wp-content/uploads/2021/10/2-1.jpg)

- The Key Provider is configured and active now

[![](http://localhost/wp-content/uploads/2021/10/3-1-300x208.jpg)](http://localhost/wp-content/uploads/2021/10/3-1.jpg)

### **Windows 11 VM Configuration**

For the Windows 11 VM configuration, I configured the following:

- Create or download a Windows 11 ISO (for more information see the blog post mentioned at the beginning).
- Copy the ISO to a datastore that can be accessed when used to install Windows 11

In the vCenter client create a new VM with the following specification:

- **Configuration step 1:** Create a new Virtual Machine
- **Configuration step 2:** Enter the Virtual Machine name
- **Configuration step 3:** Select the ESXi host or cluster for the VM
- **Configuration step 4:** Select the datastore and select **Encrypt this virtual machine**

[![](http://localhost/wp-content/uploads/2021/10/VMEncrypt-300x198.jpg)](http://localhost/wp-content/uploads/2021/10/VMEncrypt.jpg)

- **Configuration step 5: Compatibility**: ESXi 7.0 U2 and later (I’m using ESXi 7)

[![](http://localhost/wp-content/uploads/2021/10/VMGuestOS-300x197.jpg)](http://localhost/wp-content/uploads/2021/10/VMGuestOS.jpg)

- **Configuration step 6: Guest OS**: Guest OS Family: Windows 
    - Guest OS Version: Windows 10 (64-bit)
    - Enable Windows Virtualization Based Security: Check

[![](http://localhost/wp-content/uploads/2021/10/VMGuestOS-300x197.jpg)](http://localhost/wp-content/uploads/2021/10/VMGuestOS.jpg)

- **Configuration step 7: CPU:** 2 or more 
    - Memory: 4 GB or more
    - Hard disk: 64 GB or more
    - CD/DVD: Mount the ISO on the datastore
    - Custom Hardware Select **Add New Device** and choose for **Trusted Platform Module**

[![](http://localhost/wp-content/uploads/2021/10/VMADDTPM-300x241.jpg)](http://localhost/wp-content/uploads/2021/10/VMADDTPM.jpg)

[![](http://localhost/wp-content/uploads/2021/10/VMTOM-300x245.jpg)](http://localhost/wp-content/uploads/2021/10/VMTOM.jpg)

- **Configuration step 8:** VM configuration overview 
    - Click on Finish

[![](http://localhost/wp-content/uploads/2021/10/VMoverview-300x265.jpg)](http://localhost/wp-content/uploads/2021/10/VMoverview.jpg)

- Start the VM and the installation begins without complaining that this PC can’t run Windows 11

[![](http://localhost/wp-content/uploads/2021/10/VM-Boot-300x232.jpg)](http://localhost/wp-content/uploads/2021/10/VM-Boot.jpg)

Windows 11 can be installed without having a physical TPM 2.0 chipset or using the registry hack mentioned at the beginning of the blog post. How cool is that!
