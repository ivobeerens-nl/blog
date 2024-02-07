---
author: Ivo Beerens
categories:
- VMware Workstation
- windows server 2012
date: "2012-06-04T21:14:28Z"
guid: http://www.ivobeerens.nl/?p=1582
id: 1582
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- VMware
- windows server 2012
- workstation
title: Install Windows Server 2012 in VMware Workstation
url: /2012/06/04/install-windows-server-2012-in-vmware-workstation/
---

This procedure describes how to install Windows Server 2012 in VMware Workstation. The following versions are used:

- VMware Workstation Technology Preview 2012 e.x.p Build-646643
- Windows Server 2012 Release Candidate Datacenter Build 8400

In VMware Workstation Technology Preview 2012 create a new VM with the following settings:

- New Virtual Machine
- Custom (advanced)
- Workstation Tech Preview
- Select “I will install the operating system later”
- Select “Microsoft Windows” and select as version “Windows 8 x64”
- Set the Name and Location
- Minimal 1 processor, 1 core
- 2048 MB memory
- Select “Use network address translation (NAT)”
- Select “LSI Logic SAS”
- Create a new virtual disk
- SCSI
- 60 GB disk size
- Leave default disk file
- Finish
- After the VM is created, edit virtual Machine settings and browse for the Windows Server 2012 ISO in the the CD/DVD option

[![image](http://localhost/wp-content/uploads/2012/06/image_thumb.png "image")](http://localhost/wp-content/uploads/2012/06/image.png)

- Remove the VM from VMware Workstation by clicking on the X icon

[![image](http://localhost/wp-content/uploads/2012/06/image_thumb4.png "image")](http://localhost/wp-content/uploads/2012/06/image4.png)

- Edit the VMX file (i use Notepad++) and add the following line to the end to of the VMX file:

```
<pre lang="plain">vmGenCounter.enable = FALSE
```

- Add the VM back to VMware Workstation by clicking on the \*.VMX file
- During the installation choose the Windows Server 2012 Release Candidate (Server wit GUI)

[![image](http://localhost/wp-content/uploads/2012/06/image_thumb2.png "image")](http://localhost/wp-content/uploads/2012/06/image2.png)

- When the installation is ready you have a working Windows Server 2012 server

[![image](http://localhost/wp-content/uploads/2012/06/image_thumb3.png "image")](http://localhost/wp-content/uploads/2012/06/image3.png)

- Install VMware tools

More information can be found on the VMware Workstation Technology Preview 2012 [Community](http://communities.vmware.com/community/vmtn/beta/workstationtp2012?view=discussions&start=0).
