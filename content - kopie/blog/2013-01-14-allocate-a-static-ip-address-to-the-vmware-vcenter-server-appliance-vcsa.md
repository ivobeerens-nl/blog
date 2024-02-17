---
author: Ivo Beerens
categories:
- vcenter
- vcsa
date: "2013-01-14T22:15:44Z"
guid: http://www.ivobeerens.nl/?p=2113
id: 2113
ssb_fbshare_counts:
- "10"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:5;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "10"
tags:
- vCenter
- vcsa
title: Allocate a static IP address to the VMware vCenter Server Appliance (VCSA)
url: /2013/01/14/allocate-a-static-ip-address-to-the-vmware-vcenter-server-appliance-vcsa/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

When deploying the VMware vCenter Server Appliance (VCSA) it will default look for a DHCP address. When there is no DHCP server available the following error is displayed:

NO NETWORKING DETECTED.

[![image](http://localhost/wp-content/uploads/2013/01/image_thumb.png "image")](http://localhost/wp-content/uploads/2013/01/image.png)

it is possible to manually configure a static IP address by using the command line. Here are the steps:

- Open a console session of the VCSA
- Login as: **root**
- Default password is: **vmware**
- Execute the following command:

```
<pre lang="plain">/opt/vmware/share/vami/vami_config_net
```

- After executing the command, a menu is displayed. Within the menu It is possible to change the IP address, hostname, DNS, Default gateway and proxy server.

[![image](http://localhost/wp-content/uploads/2013/01/image_thumb1.png "image")](http://localhost/wp-content/uploads/2013/01/image1.png)

- After allocate a static IP Address to the VCSA the post configuration can be done by using the following URL:

```
<pre lang="plain">https://static-ip-address:5480
```
