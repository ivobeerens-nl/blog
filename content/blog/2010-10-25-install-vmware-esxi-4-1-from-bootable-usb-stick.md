---
author: Ivo Beerens
categories:
- boot
- ESXi
- usb
- vSphere
date: "2010-10-25T10:00:00Z"
guid: http://www.ivobeerens.nl/?p=699
id: 699
ssb_fbshare_counts:
- "5"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:5;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "5"
tags:
- boot
- esxi
- esxi 4.1
- usb
- VMware
- vSphere
title: Install VMware ESXi 4.1 from bootable USB stick
url: /2010/10/25/install-vmware-esxi-4-1-from-bootable-usb-stick/
---

<font color="#000000">Not all servers nowadays have a DVD player installed. Sometimes it is handy to boot from USB and installing a single VMware ESXi server. Here’s a example how to make the USB stick bootable and install VMware ESXi 4.1 from it by using Windows.</font>

<font color="#000000"></font>

**<font color="#000000">Preparation:</font>**

- <font color="#000000">Need 1GB USB memory stick or more. </font>
- <font color="#000000">Download the VMware ESXi 4.1 ISO named **VMware-VMvisor-Installer-4.1.0-260247.x86\_64.iso** (In this example I used the VMware vSphere Hypervisor version). </font>

**<font color="#ff0000">Update: The latest version of VMware ESXi is 4.1 Update 1 (VMware-VMvisor-Installer-4.1.0.update1-348481.x86\_64.iso). It solves the “Total number of sectors” bug in VMware ESXi 4.1. It is recommend to use this version so the “mod.tgz” workaround isn’t needed anymore!</font>**

- <font color="#000000">Download Syslinux, can be found by clicking on the following </font>[<font color="#000000">link</font>](http://www.kernel.org/pub/linux/utils/boot/syslinux/)<font color="#000000">. Download the latest Syslinux zip file (when writing this article syslinux-4.02.zip was the latest). </font>

**<font color="#ff0000">Update: Also tested Syslinux version 4.03. </font>**

<font color="#ff0000"></font>

<font color="#000000">Stick the USB stick on a free USB port on your computer equipped with a Windows OS. For this example I used Windows7 as Operating System. Clear the USB stick and create a partition on it by using the following command’s:</font>

- <font color="#000000">Open the command prompt and enter the following commands:</font>

<div id="codeSnippetWrapper" style="border-bottom: silver 1px solid; text-align: left; border-left: silver 1px solid; padding-bottom: 4px; line-height: 12pt; background-color: #f4f4f4; margin: 20px 0px 10px; padding-left: 4px; width: 97.5%; padding-right: 4px; font-family: 'Courier New', courier, monospace; direction: ltr; max-height: 200px; font-size: 8pt; overflow: auto; border-top: silver 1px solid; cursor: text; border-right: silver 1px solid; padding-top: 4px"><div id="codeSnippet" style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">Diskpart (make sure you run diskpart <span style="color: #0000ff">as</span> administrator) 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">list disk (list the disk <span style="color: #0000ff">in</span> your system including the USB) 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">select disk USB number 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">clean 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">create partition primary 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">active 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">format fs=fat32 quick 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">assign 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">exit
```

</div></div><font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000">To make the USB stick bootable:</font>

- <font color="#000000">Extract the Syslinux ZIP and browse to the the \\syslinux\\win32 folder, execute “**syslinux \[drive letter USB stick\]**”, example **syslinux f:** </font>
- <font color="#000000">Mount the ISO and copy all the content of the VMware ESXi 4.1 ISO to the USB stick. For mounting the ISO, I used ‘Deamon Tools Lite’ tool. </font>
- <font color="#000000">Rename the **isolinux.cfg** file to **syslinux.cfg** </font>
- <font color="#000000">Edit the syslinux.cfg and add **ks=usb** and on the end of the append line **— mod.tgz** (beware of the space between **—** and the **mod.tgz).** </font>

**<font color="#ff0000">Update: When using VMware ESXi 4.1 Update 1 the mod.tgz line doesn’t need to append!</font>**

<div id="codeSnippetWrapper" style="border-bottom: silver 1px solid; text-align: left; border-left: silver 1px solid; padding-bottom: 4px; line-height: 12pt; background-color: #f4f4f4; margin: 20px 0px 10px; padding-left: 4px; width: 97.5%; padding-right: 4px; font-family: 'Courier New', courier, monospace; direction: ltr; max-height: 200px; font-size: 8pt; overflow: auto; border-top: silver 1px solid; cursor: text; border-right: silver 1px solid; padding-top: 4px"><div id="codeSnippet" style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px"><span style="color: #0000ff">default</span> menu.c32
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">menu title VMware VMvisor Boot Menu
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">timeout 80
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px"> 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">label ESXi Installer
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">menu label ^ESXi Installer
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">kernel mboot.c32
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">append vmkboot.gz ks=usb --- vmkernel.gz --- sys.vgz --- cim.vgz --- ienviron.vgz --- install.vgz --- mod.tgz
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px"> 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">label ^Boot from local disk
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">menu label ^Boot from local disk
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">localboot 0x80
```

</div></div>- <font color="#000000">Create a **ks.cfg** file in the root from the UBS stick. For example: </font>

<div id="codeSnippetWrapper" style="border-bottom: silver 1px solid; text-align: left; border-left: silver 1px solid; padding-bottom: 4px; line-height: 12pt; background-color: #f4f4f4; margin: 20px 0px 10px; padding-left: 4px; width: 97.5%; padding-right: 4px; font-family: 'Courier New', courier, monospace; direction: ltr; max-height: 200px; font-size: 8pt; overflow: auto; border-top: silver 1px solid; cursor: text; border-right: silver 1px solid; padding-top: 4px"><div id="codeSnippet" style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">rootpw VMware01
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">install usb
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">autopart --firstdisk --overwritevmfs
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">reboot
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px"> 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">#Network install type
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">network --bootproto=<span style="color: #0000ff">static</span> --addvmportgroup=<span style="color: #0000ff">false</span> --device=vmnic0 --ip=192.168.1.10 --netmask=255.255.255.0 --gateway=192.168.1.1  --nameserver=192.168.1.1 --hostname=ESXi-01.beerens.local
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">accepteula
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px"> 
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">%firstboot --unsupported --interpreter=busybox
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">vim-cmd hostsvc/datastore/rename datastore1 <span style="color: #006080">"$(hostname -s)-local-storage-1"</span>
```

</div></div>- <font color="#000000">Copy the syslinux-4.02\\com32\\mboot\\**mboot.c32** file the USB stick (overwrite the old file on the USB stick) </font>
- <font color="#000000">Copy the syslinux-4.02\\com32\\menu\\**menu.c32** file the USB stick (overwrite the old file on the USB stick) </font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000">The bootable VMware ESXi 4.1 stick is ready for use. When booting the USB stick the following message is displayed “**Total number of sectors not a multiple of sectors per track! Add mtools\_skip\_check=1 to your .mtoolsrc file to skip this test**”.</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2010/10/image_thumb1.png "image")</font>](http://localhost/wp-content/uploads/2010/10/image1.png)

<font color="#000000"></font>

**<font color="#ff0000">Update: When using VMware ESXi 4.1 Update 1 this bug is fixed. You’re ready to use the USB stick!</font>**

<font color="#000000">On the VMware communities I found the following </font>[<font color="#000000">post</font>](http://communities.vmware.com/message/1621352)<font color="#000000">. This post states a manual solution by using the following commands:</font>

- <font color="#000000">Press ALT-F1 </font>
- <font color="#000000">Login by using the root account with no password </font>
- **<font color="#000000">echo “mtools\_skip\_check=1”>.\\mtoolsrc </font>**
- <font color="#000000">ALT+F2 and return to the orginal Console window </font>
- <font color="#000000">Press ENTER or wait to continue </font>

<font color="#000000">To automate the above solution read the following blogpost “**VMware ESX 4.1 install using Western Digital USB Hard Drive”** . By using this blogpost I created a mod.tgz file by using the following commands from a full installation of VMware ESXi 4.1:</font>

- <font color="#000000">Login the VMware ESXi 4.1 console </font>
- <font color="#000000">Make a directory in the root for example mkdir temp </font>
- <font color="#000000">cd temp </font>
- <font color="#000000">mkdir –p etc/vmware/init/init.d/ </font>
- <font color="#000000">cd etc/vmware/init/init.d/ </font>
- <font color="#000000">vi 47.mtoolshack</font>

<div id="codeSnippetWrapper" style="border-bottom: silver 1px solid; text-align: left; border-left: silver 1px solid; padding-bottom: 4px; line-height: 12pt; background-color: #f4f4f4; margin: 20px 0px 10px; padding-left: 4px; width: 97.5%; padding-right: 4px; font-family: 'Courier New', courier, monospace; direction: ltr; max-height: 200px; font-size: 8pt; overflow: auto; border-top: silver 1px solid; cursor: text; border-right: silver 1px solid; padding-top: 4px"><div id="codeSnippet" style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: white; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px">echo <span style="color: #006080">"mtools_skip_check=1"</span> >/.mtoolsrc
```

```
<pre style="border-bottom-style: none; text-align: left; padding-bottom: 0px; line-height: 12pt; background-color: #f4f4f4; margin: 0em; border-left-style: none; padding-left: 0px; width: 100%; padding-right: 0px; font-family: 'Courier New', courier, monospace; direction: ltr; border-top-style: none; color: black; border-right-style: none; font-size: 8pt; overflow: visible; padding-top: 0px"><span style="color: #0000ff">return</span> ${SUCCESS}
```

</div></div>- <font color="#000000">Save the fi using the command **:wq** in VI </font>
- <font color="#000000">cd /temp </font>
- <font color="#000000">tar czvf mod.tgz etc </font>
- <font color="#000000">SCP the file **mod.tgz** file to the USB stick </font>

<font color="#000000">The mod.tgz can also downloaded, so the above steps can be skiped. </font><font color="#000000">On the end of this article is a download link for the mod.tgz. </font>

<font color="#000000">The mod.tgz contains an init script which skips the mtools check. </font><font color="#000000">Now you’re ready to boot your server with the USB stick and your able to install VMware ESXi 4.1. </font>

#### [Download mod.tgz](http://localhost/wp-content/uploads/mod.tgz)

**<font color="#ff0000">Update : When using VMware ESXi 4.1 Update 1 there is no need to add the mod.tgz because this bug is fixed. </font>**

\[ad#banner\]
