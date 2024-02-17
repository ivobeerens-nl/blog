---
title: "Enable the vShield driver in VMware tools"
date: "2013-07-11T12:46:50.000Z"
categories: 
  - "esxi"
  - "vshield"
tags: 
  - "esxi-2"
  - "vshield"
author: Ivo Beerens
---

Here are the manually steps when the VMware tools already are installed:

- In the vSphere client open a Console session
- Select VM – Guest – Install/Upgrade VMware Tools
- Choose Interactive Tools Upgrade

[![image](images/image_thumb.png "image")](images/image.png)

- In the VM open the setup program

[![image](images/image_thumb1.png "image")](images/image1.png)

- Choose Next

[![image](images/image_thumb2.png "image")](images/image2.png)

- Choose Modify

[![image](images/image_thumb3.png "image")](images/image3.png)

- Expand the VMCI Driver section, select  vShield Drivers and  select “This feature will be installed on the local hard drive”

[![image](images/image_thumb4.png "image")](images/image4.png)

- Next – modify

If you are installing VMware Tools in a number of Windows virtual machines, you can automate its installation by using the following syntax:

- Mount/Extract the VMware Tools ISO

setup.exe /S /v /qn REBOOT=R ADDLOCAL=VMCI REMOVE=Hgfs

or choose Automatic Tools Upgrade 

[![image](images/image_thumb5.png "image")](images/image5.png)

In the advanced Options field enter:

/v /qn ADDLOCAL=VMCI,VShield REMOVE=Hgfs



