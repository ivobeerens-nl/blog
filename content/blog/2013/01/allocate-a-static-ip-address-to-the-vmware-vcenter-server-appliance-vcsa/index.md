---
title: "Allocate a static IP address to the VMware vCenter Server Appliance (VCSA)"
date: "2013-01-14T21:15:44.000Z"
categories: 
  - "vcenter-2"
  - "vcsa"
tags: 
  - "vcenter"
  - "vcsa"
author: Ivo Beerens
---

NO NETWORKING DETECTED.

[![image](images/image_thumb.png "image")](images/image.png)

it is possible to manually configure a static IP address by using the command line. Here are the steps:

- Open a console session of the VCSA 
- Login as: **root**
- Default password is: **VMware**
- Execute the following command:

/opt/VMware/share/vami/vami\_config\_net

- After executing the command, a menu is displayed. Within the menu It is possible to change the IP address, hostname, DNS, Default gateway and proxy server.

[![image](images/image_thumb1.png "image")](images/image1.png)

- After allocate a static IP Address to the VCSA the post configuration can be done by using the following URL: 

https://static-ip-address:5480



