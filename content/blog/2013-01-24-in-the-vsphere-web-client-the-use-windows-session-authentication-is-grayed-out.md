---
author: Ivo Beerens
categories:
- VMware
- vsphere51
date: "2013-01-24T10:44:15Z"
guid: http://www.ivobeerens.nl/?p=2146
id: 2146
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- VMware
- vsphere51
title: In the vSphere Web Client the &ldquo;Use Windows session authentication&rdquo;
  is grayed out
url: /2013/01/24/in-the-vsphere-web-client-the-use-windows-session-authentication-is-grayed-out/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

When logging in the vSphere Web Client login page the “Use Windows session Authentication” check box is grayed out. To solve this you need to install the Client Integration Plug-in.

The Client Integration Plug-in provides:

- Access to the VM console
- Deploy OVF or OVA templates
- Transfer files with the datastore browser
- Use Windows Session authentication

Without the VMware Client Integration Plug-in, the “Use Windows session Authentication” check box is grayed out (1) in the vSphere Web Client login page.

[![image](http://localhost/wp-content/uploads/2013/01/image_thumb6.png "image")](http://localhost/wp-content/uploads/2013/01/image6.png)

After installing the VMware Client Integration Plug-in (2) from the vSphere Web Client login page, the Use Windows session Authentication check box option can be checked and the current login setting are used in the vSphere Web Client.

[![image](http://localhost/wp-content/uploads/2013/01/image_thumb7.png "image")](http://localhost/wp-content/uploads/2013/01/image7.png)
