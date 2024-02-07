---
author: Ivo Beerens
categories:
- ESXi
- kickstart
- pxe
- scripted
date: "2011-09-20T15:53:30Z"
guid: http://www.ivobeerens.nl/2011/09/20/create-vmware-esxi-5-pxe-unattended-scripted-installation-using-windows/
id: 1088
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- esxi
- kickstart
- pxe
- scripted
title: Create a VMware ESXi 5 PXE unattended scripted installation using Windows
url: /2011/09/20/create-vmware-esxi-5-pxe-unattended-scripted-installation-using-windows/
---

<span style="color: #000000;">The most information available on how-to perform a unattended scripted installation of VMware ESXi 5 is based on Linux. Here is a procedure how-to create a scripted installation of VMware ESXi 5 using Microsoft Windows. </span>

<span style="color: #000000;">Here is an overview of the boot process:</span>

[![image](http://localhost/wp-content/uploads/2011/09/image_thumb11.png "image")](http://localhost/wp-content/uploads/2011/09/image12.png)

#### <span style="color: #000000;">What do we need</span>

<span style="color: #000000;">The following software must be downloaded:</span>

<span style="color: #000000;">– </span>[<span style="color: #000000;">Syslinux 3.86</span>](http://www.kernel.org/pub/linux/utils/boot/syslinux/)<span style="color: #000000;"> (This is the Syslinux version VMware supports)</span>

<span style="color: #000000;">– </span>[<span style="color: #000000;">FileZilla Server 0\_9\_39</span>](http://filezilla-project.org/download.php?type=server)

<span style="color: #000000;">– </span>[<span style="color: #000000;">TFTPD 4.00</span>](http://tftpd32.jounin.net/)

<span style="color: #000000;">– </span>[<span style="color: #000000;">Notepad ++</span>](http://notepad-plus-plus.org/)

<span style="color: #000000;">– </span>[<span style="color: #000000;">VMware ESXi 5 ISO</span>](http://downloads.vmware.com/d/info/datacenter_cloud_infrastructure/vmware_vsphere/5_0)

#### Step 1 Windows XP

<span style="color: #000000;">This procedure is tested with Microsoft Windows XP SP2. The following requirements must be met: </span>

<span style="color: #000000;">– In Windows XP use a fixed IP. In this example we use 192.168.1.1/24 IP address</span>

<span style="color: #000000;">– Make sure there is enough free disk space available (approximately 500 MB needed)</span>

<span style="color: #000000;">– Disable the Windows firewall</span>

#### Step 2 Create directory structure

<span style="color: #000000;">Create the following directory structure in the root of the C: partition:</span>

```
<pre lang="plain">C:\PXEboot
C:\PXEboot\pxelinux.cfg
C:\PXEboot\kickstart
```

#### Step 3 Copy the content of the ESXi 5 ISO

<span style="color: #000000;">Mount the VMware ESXi 5 ISO and copy the content to the *c:\\PXEboot* directory</span>

#### Step 4 Copy the Syslinux files

<span style="color: #000000;">The Syslinux files allow the target ESXi server to boot the ESXi installer. </span>

<span style="color: #000000;">– Extract Syslinux 3.86 and:</span>

<span style="color: #000000;">– Copy the *pxelinux.0* and *menu.c32* files to the C:\\PXEboot directory. </span>

<span style="color: #000000;">– Overwrite the menu.c32 file</span>

#### <span style="color: #000000;">Step 5 Install &amp; Configure tftpd32</span>

<span style="color: #000000;">The Tftpd32 utility gets the function DHCP and TFTP server. </span>

<span style="color: #000000;">– Run Tftpd32.exe and make the following configuration settings:</span>

| [![image](http://localhost/wp-content/uploads/2011/09/image_thumb12.png "image")](http://localhost/wp-content/uploads/2011/09/image13.png) | [![image](http://localhost/wp-content/uploads/2011/09/image_thumb13.png "image")](http://localhost/wp-content/uploads/2011/09/image14.png) |
|---|---|
| <span style="color: #000000;">Choose:   – TFTP Server   – DHCP Server</span> | <span style="color: #000000;">Point the base directory to c:\\PXEboot</span> |
| [![image](http://localhost/wp-content/uploads/2011/09/image_thumb14.png "image")](http://localhost/wp-content/uploads/2011/09/image15.png) | [![image](http://localhost/wp-content/uploads/2011/09/image_thumb15.png "image")](http://localhost/wp-content/uploads/2011/09/image16.png) |
| <span style="color: #000000;">Create a DHCP range</span> | <span style="color: #000000;"><span style="color: #000000;">Edit the ini file c:\\program files\\tftpd32\\tftpd32.ini</span></span>Add the DHCP options   066 with DHCP server IP address   067 pxelinux.0 |

<span style="color: #000000;">– Restart and run the tftpd32.exe utility</span>

#### Step 6 Install &amp; configure FileZilla server

<span style="color: #000000;">– Install the FileZilla Server with the default settings</span>

<span style="color: #000000;">– Create a user username: vmware password: vmware</span>

[![image](http://localhost/wp-content/uploads/2011/09/image_thumb16.png "image")](http://localhost/wp-content/uploads/2011/09/image17.png)

<span style="color: #000000;">– Add a shared folder c:\\PXEboot\\Kickstart folder with the default rights</span>

[<span style="color: #000000;">![2011-09-19 18h32_16](http://localhost/wp-content/uploads/2011/09/2011-09-19-18h32_16_thumb.jpg "2011-09-19 18h32_16")</span>](http://localhost/wp-content/uploads/2011/09/2011-09-19-18h32_16.jpg)

#### <span style="color: #000000;">Step 7 Create default file</span>

<span style="color: #000000;">Create a file named *default* (Use notepad ++ for the file creation) and save the file in the C:\\PXEboot\\pxelinux.cfg directory. Here is an example default script:</span>

```
<pre lang="plain">DEFAULT menu.c32
MENU TITLE ESXi 5 Boot menu
NOHALT 1
PROMPT 0
TIMEOUT 80

LABEL install 
 KERNEL mboot.c32 
 APPEND -c boot.cfg 
 MENU LABEL ^ESXi-5 Interactively install

Label ESXi 5 install scripted 
 KERNEL mboot.c32 
 APPEND -c boot.cfg ks=ftp://vmware:vmware@192.168.1.1/ks.cfg +++ 
 MENU LABEL ^ESXi5-01 Scripted install 
 IPAPPEND 1

LABEL hddboot 
 LOCALBOOT 0x80 
 MENU LABEL ^Boot from local disk
```

<span style="color: #000000;">If you want to install more VMware ESXi 5 servers you can add extra entries in the default file and point them to separate Kickstart file.</span>

```
```

#### Step 8 Create ks.cfg file

<span style="color: #000000;">Create a Kickstart file named *ks.cfg* (Use notepad ++ for the file creation ) and place the file in the *c:\\PXEboot\\Kickstart* directory. Here is a sample ks.cfg script:</span>

```
<pre lang="plain">#Sample kickstart scripted installation
vmaccepteula
rootpw VMw@re
install --firstdisk --overwritevmfs
network --bootproto=static --ip=192.168.250.21 --gateway=192.168.250.1 --nameserver=192.168.250.6 --netmask=255.255.255.0 --hostname=esxi5-01.beerens.local --device=vmnic0 --addvmportgroup=0
reboot

%firstboot --interpreter=busybox
# Rename local datastore name
vim-cmd hostsvc/datastore/rename datastore1 "$(hostname -s)-local-storage-1"
# DNS names
esxcli system hostname set --fqdn=esxi5-01.beerens.local
esxcli network ip dns search add --domain=beerens.local
# DNS server addresses
esxcli network ip dns server add --server=192.168.250.6
esxcli network ip dns server add --server=192.168.250.1
# SSH and ESXi shell
vim-cmd hostsvc/enable_ssh
vim-cmd hostsvc/start_ssh
vim-cmd hostsvc/enable_esx_shell
vim-cmd hostsvc/start_esx_shell
```

#### Step 9 Test the installation

<span style="color: #000000;">Boot the server and select *ESXi5-01 Scripted Install* option to test the scripted installation. </span>

[![image](http://localhost/wp-content/uploads/2011/09/image_thumb17.png "image")](http://localhost/wp-content/uploads/2011/09/image18.png)

\[ad#banner\]
