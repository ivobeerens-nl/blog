---
title: "Upgrading Single Sign-On 5.1 to vCenter Single Sign-On 5.5 post task"
date: "2013-11-11T17:31:55.000Z"
categories: 
  - "sso"
  - "vcenter-2"
  - "vsphere"
tags: 
  - "sso"
  - "vmware"
  - "vsphere"
---

With vCenter Single Sign-On (SSO) 5.5 there is no requirement for a SQL database anymore. SSO 5.5 uses a own VMware Directory Service (VMdir) database. So after the upgrade to SSO 5.5,  the Single Sign-On 5.1  database and users can be removed. This is a manual process. In SQL Management Studio remove the SSO (RSA) database and the “ RSA\_DBA” and “ RSA\_USER” users created.

[![image](images/image_thumb.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2013/11/image.png)
