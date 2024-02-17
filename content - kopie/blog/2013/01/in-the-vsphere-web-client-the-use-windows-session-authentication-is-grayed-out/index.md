---
title: "In the vSphere Web Client the &ldquo;Use Windows session authentication&rdquo; is grayed out"
date: "2013-01-24T09:44:15.000Z"
categories: 
  - "vmware"
  - "vsphere51"
tags: 
  - "vmware"
  - "vsphere51"
---

When logging in the vSphere Web Client login page the “Use Windows session Authentication” check box is grayed out. To solve this you need to install the Client Integration Plug-in.

The Client  Integration Plug-in provides:

- Access to the VM console
- Deploy OVF or OVA templates
- Transfer files with the datastore browser
- Use Windows Session authentication

Without the VMware Client Integration Plug-in, the “Use Windows session Authentication” check box is grayed out (1) in the vSphere Web Client login page.

[![image](images/image_thumb6.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2013/01/image6.png)

After installing the VMware Client Integration Plug-in (2) from the vSphere Web Client login page, the Use Windows session Authentication check box option can be checked and the current login setting are used in the vSphere Web Client.

[![image](images/image_thumb7.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2013/01/image7.png)
