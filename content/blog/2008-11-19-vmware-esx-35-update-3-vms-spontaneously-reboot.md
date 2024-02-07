---
aktt_notify_twitter:
- "no"
author: Ivo Beerens
categories:
- Update
- VMware
- VMware 3.5 Update 3
date: "2008-11-19T11:51:12Z"
guid: http://www.ivobeerens.nl/?p=180
id: 180
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Patches
- VMware 3.5 Update 3
title: VMware ESX 3.5 Update 3 VM&#8217;s spontaneously reboot.
url: /2008/11/19/vmware-esx-35-update-3-vms-spontaneously-reboot/
---

A week ago i upgraded a customers environment to VMware ESX 3.5 Update 3 and VC 2.5 Update 3. After the upgrade some Virtual Machines (VM) spontaneously rebooted. After investing the problem we saw that after a VMotion action the spontaneously reboot occurred.

We disabled in HA the option “Virtual Machine Monitoring” and set DRS to manual. The problem with Virtual Machine monitoring is:

> <span lang="N">The Virtual Machine heartbeats are being dropped which is triggered by Vmotion and the VM gets reset by the HA feature as it thinks it has gone offline. Since the feature is now off it should be safe to turn on DRS again. </span>

There are more people who have this problem, read the following post on the VMware forum, [3.5U3 – any guinea pigs yet?](http://communities.vmware.com/thread/178417?tstart=0&start=0).

I made a support request @ VMware. The told me today that 20 November patch 10 for VMware 3.5 Update 3 will be released. Patch 10 fixes SOME random reboot problems in Update 3. I hope it resolves this nasty issue.
