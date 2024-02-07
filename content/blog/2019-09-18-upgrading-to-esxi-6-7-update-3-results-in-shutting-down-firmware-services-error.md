---
author: Ivo Beerens
categories:
- ESXi
date: "2019-09-18T14:12:05Z"
guid: https://www.ivobeerens.nl/?p=7112
id: 7112
ssb_old_counts:
- a:6:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- esxi
- VMware
title: 'Boot error: Shutting down firmware services&#8230; error after upgrading to
  VMware ESXi 6.7 Update 3'
url: /2019/09/18/upgrading-to-esxi-6-7-update-3-results-in-shutting-down-firmware-services-error/
---

After upgrading one of my home lab servers to VMware ESXi 6.7 Update 3, I’ve got the following error when trying to boot:

[![](http://localhost/wp-content/uploads/2019/09/error-300x177.jpg)](http://localhost/wp-content/uploads/2019/09/error.jpg)

> Shutting down firmware services…
> 
> Page allocation error: Out of resources
> 
> Failed to shutdown the boot services.
> 
> Unrecoverable error

After changing the boot mode from UEFI to “legacy only” in the BIOS, the ESXi host booted without the error.

[![](http://localhost/wp-content/uploads/2019/09/bios-300x141.jpg)](http://localhost/wp-content/uploads/2019/09/bios.jpg)

VMware has confirmed that this is a bug. There is VMware community thread ([link](https://communities.vmware.com/thread/617099)) about this bug and two other workarounds. When there will be a permanent fix available is unclear at the moment.
