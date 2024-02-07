---
author: Ivo Beerens
categories:
- ESXi
- VMware
date: "2014-02-27T15:22:33Z"
guid: http://www.ivobeerens.nl/?p=2682
id: 2682
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- esxi
- VMware
title: vSphere 5.x NIC problems
url: /2014/02/27/vsphere-5-x-nic-problems/
---

Last week ik blogged about the “Broadcom adapter data corruption on ESXi/ESX hosts using the tg3 driver and TSO enabled” NIC problem. [Link](http://localhost/2014/02/19/vmware-esxi-broadcom-data-corruption-problem-with-tg3-driver-check-your-environment/) This week I found two new vSphere NIC issues worth to mention:

- Hosts with virtual machines using the E1000/E1000E adapter have networking issues after upgrading to ESXi 5.1 U2 (2072694). [Link](http://kb.vmware.com/selfservice/microsites/search.do?cmd=displayKC&docType=kc&externalId=2072694)
- ESXi 5.x host experiences a purple diagnostic screen mentioning E1000PollRxRing and E1000DevRx (2059053). [Link](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2059053)
