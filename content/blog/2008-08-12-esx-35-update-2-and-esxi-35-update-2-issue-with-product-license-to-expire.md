---
author: Ivo Beerens
categories:
- 3i
- Update
- VMware
- VMware 3.5 Update 2
date: "2008-08-12T10:36:53Z"
guid: http://www.ivobeerens.nl/?p=68
id: 68
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- BUG
- VMware 3.5 Update 2
title: ESX 3.5 Update 2 and ESXi 3.5 Update 2 issue with product license to expire
url: /2008/08/12/esx-35-update-2-and-esxi-35-update-2-issue-with-product-license-to-expire/
---

 You got the following error when powering on a VM:

Unable to Power On virtual machine with “A General System error occurred: Internal error”

<span style="font-size: x-small; font-family: Arial;"><span style="font-size: 10pt; font-family: arial;">An issue has been uncovered with ESX 3.5 Update 2 and ESXi 3.5 Update 2 that causes the product license to expire on August 12. VMware is alerting customers and partners of this issue. VMware regrets the inconvenience caused to customers. Updated product bits with correct licensing will be made available for download as soon as possible. </span></span>

<span style="font-size: x-small; font-family: Arial;"> </span>

<div class="MsoNormal"><span style="font-size: x-small; font-family: Arial;"><span style="font-size: 10pt; font-family: arial;">The work-around: turn off NTP (if you’re using it), and then manually set the date of all ESX 3.5u2 hosts back to 10th of August. This can be done either through the VI Client (Host -> Configuration -> Time Configuration) or by typing date -s “08/10/2008” at the Service Console command line on the ESX hosts. </span></span></div><span style="font-size: x-small; font-family: Arial;"> </span>

<span style="font-size: x-small; font-family: Arial;"><span style="font-size: 10pt; font-family: arial;">This seems to affect initial VM power-on (including from suspended state) and VMotion.</span></span>

<span style="font-size: x-small; font-family: Arial;"><span style="font-size: 10pt; font-family: arial;">On the VMTN forum there is a thread post about this problem, check it [here](http://communities.vmware.com/thread/162377?tstart=0)</span></span>

<div class="MsoNormal"><span style="font-size: x-small; font-family: Arial;">**Update:** VMware has created a KB article:

Unable to Power On virtual machine with “A General System error occurred: Internal error”

 [http://kb.vmware.com/selfservice/dynamickc.do?externalId=1006716&amp;sliceId=1&amp;command=show&amp;forward=nonthreadedKC&amp;kcId=1006716](http://kb.vmware.com/selfservice/dynamickc.do?externalId=1006716&sliceId=1&command=show&forward=nonthreadedKC&kcId=1006716)

</span></div><span style="font-size: x-small; font-family: Arial;"> </span>
