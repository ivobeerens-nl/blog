---
author: Ivo Beerens
categories:
- ESXi
- vshield
date: "2013-07-11T14:46:50Z"
guid: http://www.ivobeerens.nl/?p=2383
id: 2383
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- esxi
- vshield
title: Enable the vShield driver in VMware tools
url: /2013/07/11/enable-the-vshield-driver-in-vmware-tools/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

One of the steps of a vShield Endpoint based deployment is to enable the vShield driver in VMware tools. The vShield driver is not enabled by default. This can be done manually or automatically for example in the golden image of a VDI desktop.

Here are the manually steps when the VMware tools already are installed:

- In the vSphere client open a Console session
- Select VM – Guest – Install/Upgrade VMware Tools
- Choose Interactive Tools Upgrade

[![image](http://localhost/wp-content/uploads/2013/07/image_thumb.png "image")](http://localhost/wp-content/uploads/2013/07/image.png)

- In the VM open the setup program

[![image](http://localhost/wp-content/uploads/2013/07/image_thumb1.png "image")](http://localhost/wp-content/uploads/2013/07/image1.png)

- Choose Next

[![image](http://localhost/wp-content/uploads/2013/07/image_thumb2.png "image")](http://localhost/wp-content/uploads/2013/07/image2.png)

- Choose Modify

[![image](http://localhost/wp-content/uploads/2013/07/image_thumb3.png "image")](http://localhost/wp-content/uploads/2013/07/image3.png)

- Expand the VMCI Driver section, select vShield Drivers and select “This feature will be installed on the local hard drive”

[![image](http://localhost/wp-content/uploads/2013/07/image_thumb4.png "image")](http://localhost/wp-content/uploads/2013/07/image4.png)

- Next – modify

If you are installing VMware Tools in a number of Windows virtual machines, you can automate its installation by using the following syntax:

- Mount/Extract the VMware Tools ISO

```
<pre lang="plain">setup.exe /S /v /qn REBOOT=R ADDLOCAL=VMCI REMOVE=Hgfs
```

or choose Automatic Tools Upgrade

[![image](http://localhost/wp-content/uploads/2013/07/image_thumb5.png "image")](http://localhost/wp-content/uploads/2013/07/image5.png)

In the advanced Options field enter:

```
<pre lang="plain">/v /qn ADDLOCAL=VMCI,VShield REMOVE=Hgfs
```
