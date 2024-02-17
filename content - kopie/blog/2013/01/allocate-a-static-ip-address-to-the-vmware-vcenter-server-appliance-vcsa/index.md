---
title: "Allocate a static IP address to the VMware vCenter Server Appliance (VCSA)"
date: "2013-01-14T21:15:44.000Z"
categories: 
  - "vcenter-2"
  - "vcsa"
tags: 
  - "vcenter"
  - "vcsa"
---

When deploying the VMware vCenter Server Appliance (VCSA) it will default look for a DHCP address. When there is no DHCP server available the following error is displayed:

NO NETWORKING DETECTED.

[![image](images/image_thumb.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2013/01/image.png)

it is possible to manually configure a static IP address by using the command line. Here are the steps:

- Open a console session of the VCSA 
- Login as: **root**
- Default password is: **vmware**
- Execute the following command:

/opt/vmware/share/vami/vami\_config\_net

- After executing the command, a menu is displayed. Within the menu It is possible to change the IP address, hostname, DNS, Default gateway and proxy server.

[![image](images/image_thumb1.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2013/01/image1.png)

- After allocate a static IP Address to the VCSA the post configuration can be done by using the following URL: 

https://static-ip-address:5480
