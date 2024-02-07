---
author: Ivo Beerens
categories:
- vdp
- vsphere data protection
date: "2012-09-21T11:01:05Z"
guid: http://www.ivobeerens.nl/?p=1898
id: 1898
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- vdp
- vsphere data protection
title: Implementing vSphere Data Protection (VDP)  tips
url: /2012/09/21/implementing-vsphere-data-protection-vdp-tips/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

vSphere Data Protection (VDP) is replacing VMware Data Recovery (vDR). VDP is a more robust product based on the EMC Avamar product.

Here are some VDP implementing tips:

- Each vCenter server can support up to 10 VDP appiances
- Each VDP appliance supports up to 100 VMs
- VDP stores deduplicated data on the 0.5,1 or 2 TB datastores.
- It is not possible to use CIFS or NFS shares directly from the VDP appliance.
- VDP comes in 3 different OVA sizes 0,5TB, 1TB and 2TB. Amount of disk space needed:

| **OVA Size (TB)** | **Disk Space Required (GB)** |
|---|---|
| 0,5 | 850 |
| 1 | 1600 (1,57 TB) |
| 2 | 3100 (3,02 TB) |

- It is not possible to expand the VDP destination datastore
- VDP is managed by the vSphere Web client
- At least one vCenter 5.1 server is required
- VDP is included in vSphere 5.1 Essentials Plus and higher
- To configure the VDP appliance use the following URL: ***https://ip** **appliance:8543/vdp-configure/***
- The default username is ***root*** and the password is ***changeme***
- For the VDP vCenter registration use formats as in the screenshot:

[![image](http://localhost/wp-content/uploads/2012/09/image_thumb10.png "image")](http://localhost/wp-content/uploads/2012/09/image11.png)


- After the VDP is configured the following URL can be used to do some configuration and maintenance: ***https://<ip* *address of VDP appliance>:8543/vdp-configure/***

[![image](http://localhost/wp-content/uploads/2012/09/image_thumb11.png "image")](http://localhost/wp-content/uploads/2012/09/image12.png)

- VDP supports up to 8 simultaneously backups of 8 VMs

More information on VDP can be found here:

- [vSphere Data Protection Administration Guide](http://pubs.vmware.com/vsphere-51/topic/com.vmware.ICbase/PDF/vmware-data-protection-administration-guide-51.pdf)
- [VMware Data Protection (VDP) FAQ](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2016565)
