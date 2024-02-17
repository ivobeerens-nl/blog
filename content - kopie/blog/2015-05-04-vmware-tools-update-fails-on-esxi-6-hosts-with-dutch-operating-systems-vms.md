---
author: Ivo Beerens
categories:
- ESXi
- VMware
date: "2015-05-04T11:35:04Z"
guid: http://www.ivobeerens.nl/?p=3762
id: 3762
ssb_fbshare_counts:
- "3"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:3;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "3"
tags:
- esxi
- VMware
- vmware horizon view
title: VMware tools update fails on ESXi 6 hosts with Dutch Operating System VMs
url: /2015/05/04/vmware-tools-update-fails-on-esxi-6-hosts-with-dutch-operating-systems-vms/
---

After upgrading all the hosts in the lab environment to VMware ESXi 6, I tried to upgrade the VMware tools version of a Dutch Windows 7 golden VM used by VMware Horizon View. The VMware tools upgrade fails with the following message:

> VMware Tools Setup Wizard ended prematurely

[![vmware tools](http://localhost/wp-content/uploads/2015/05/vmware-tools-300x234.png)](http://localhost/wp-content/uploads/2015/05/vmware-tools.png)

This is a known bug in VMware ESXi 6.0 with Dutch Operating System VMs (see KB, [link](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2114476)).

The following work around can be used:

- Create a local group named “everyone”
- Add the user used for installing VMware tools to the “everyone” group
- Run the VMware tools upgrade
- Remove the “everyone” group
