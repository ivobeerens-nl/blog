---
author: Ivo Beerens
categories:
- sso
- vcenter
date: "2013-05-30T11:24:48Z"
guid: http://www.ivobeerens.nl/?p=2270
id: 2270
ssb_fbshare_counts:
- "3"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:3;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "3"
tags:
- sso
- vCenter
title: vCenter Single Sign On (SSO) password reset
url: /2013/05/30/vcenter-single-sign-on-sso-password-reset/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

During the installation of the Windows vCenter Single Sing On (SSO) service you must provide a password for the SSO admin user named “[admin@System-Domain](mailto:“admin@System-Domain)”.

[![image](http://localhost/wp-content/uploads/2013/05/image_thumb.png "image")](http://localhost/wp-content/uploads/2013/05/image.png)

The password you enter is called the master password. If you change the master password, the password entered during the installation of the SSO service is needed as master password for resetting the “[admin@System-Domain](mailto:“admin@System-Domain)”. You can reset it by using the following syntax:

- navigate to the following directory “\\Program Files\\VMware\\Infrastructure\\SSOServer\\utils”
- Use the “rsautil reset-admin-password” command. The VMware KB article can be found [here](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2034608).

**If you forgot the master password and have no other admin account, there is no supported way to reset the SSO password. You need to reinstall your vCenter environment!**

There is an unsupported way to recover the SSO password by reading the sha256 hashed password. The complete procedure can be found on [Schubis Blog](http://www.die-schubis.de/doku.php?id=vmware:vsphere&&_sm_au_=iVVqjkrsQ0sLqFW6).

Make sure that you document master SSO password entered during the installation. After the installation add some other users to Administrators group in SSO. I hope VMware will make it possible to reset the “[admin@System-Domain](mailto:“admin@System-Domain)” password. in a future patch of release.
