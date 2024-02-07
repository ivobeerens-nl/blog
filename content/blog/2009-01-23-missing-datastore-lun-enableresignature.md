---
aktt_notify_twitter:
- "no"
author: Ivo Beerens
categories:
- VirtualCenter
- VMware
date: "2009-01-23T16:18:32Z"
guid: http://www.ivobeerens.nl/?p=286
id: 286
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
title: Missing datastore (LUN), EnableResignature
url: /2009/01/23/missing-datastore-lun-enableresignature/
---

 <span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><font size="+0"><span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><font color="#000000" face="TheMix B3 Light" size="3"><span class="Apple-style-span" style="word-spacing: 0px; font: 11px/17px verdana; text-transform: none; color: rgb(0,0,0); text-indent: 0px; white-space: normal; letter-spacing: normal; border-collapse: separate; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0"><span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><span class="Apple-style-span" style="word-spacing: 0px; font: 11px/17px verdana; text-transform: none; color: rgb(0,0,0); text-indent: 0px; white-space: normal; letter-spacing: normal; border-collapse: separate; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0"> </span></span></span></font></span></font></span>

<span style="font-size: 10pt; font-family: "Verdana","sans-serif"">Yesterday a customer called me that one of the VMware ESX hosts is missing 1 datastore (LUN). The other VMware ESX hosts in the cluster had no problems with the datastore. Looked in the NetApp filer to see the presentation of the LUN, everything was okay. </span>

<span style="font-size: 10pt; font-family: "Verdana","sans-serif"">After investing the log files on the VMware ESX host i found the following message: </span>

> **<span style="font-weight: normal; font-size: 10pt; font-family: "Verdana","sans-serif"; mso-bidi-font-weight: bold">Jan 22 12:39:34 boz101 vmkernel: 152:21:01:58.702 cpu4:1040)ALERT: LVM: 4476: vml.020003000060a980004335434b464a4b77554e59744c554e202020:1 may be snapshot: disabling access. See resignaturing section in SAN config guide</span>**<span style="font-size: 10pt; font-family: "Verdana","sans-serif"">. </span>

<span style="font-size: 10pt; color: black; font-family: "Verdana","sans-serif"">It seems that the VMFS volume has been detected with a different LUN ID. The LUN ID is stored in the LVM header of the volume. When the LUN ID changes you need to enable resignature option to see the datastore again.</span><span style="font-size: 10pt; font-family: "Verdana","sans-serif""> </span>

<span style="font-size: 10pt; color: black; font-family: "Verdana","sans-serif"">In the evening we powered all VMs on that LUN down. On the host that was missing the datastore, I enabled the resignaturing option by:</span><span style="font-size: 10pt; font-family: "Verdana","sans-serif""> </span>

<span style="font-size: 10pt; color: black; font-family: "Verdana","sans-serif"">– Go to the configuration tab of the VMware ESX host and select Advanced settings</span><span style="font-size: 10pt; font-family: "Verdana","sans-serif""> </span>

<span style="font-size: 10pt; color: black; font-family: "Verdana","sans-serif"">– Click on LVM, and changed the <span class="apple-style-span"><span style="word-spacing: 0px; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0">EnableResignature 0 (off) in 1 (on). </span></span></span><span style="font-size: 10pt; font-family: "Verdana","sans-serif""></span>

<span class="apple-style-span"><span style="font-size: 10pt; color: black; font-family: "Verdana","sans-serif""><span style="word-spacing: 0px; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0">Did a rescan on the VMware ESX host and the LUN appeared as “SNAP-17EABCCC-VMWARE-LUN-03”. Tried the change the “SNAP-17EABCCC-VMWARE-LUN-03” LUN back to the old name “VMWARE-LUN-03”, the following message appeared:</span></span></span>

> <span class="apple-style-span"><span style="font-size: 10pt; color: black; font-family: "Verdana","sans-serif""><span style="word-spacing: 0px; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0">The name “VMWARE-LUN-03” already exists. </span></span></span><span style="font-size: 10pt; font-family: "Verdana","sans-serif""></span>

<span class="apple-style-span"><span style="font-size: 10pt; color: black; font-family: "Verdana","sans-serif""><span style="word-spacing: 0px; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0">The solution was to switch the view to DATASTORES in vCenter and unregister all VMs on the “SNAP-17EABCCC-VMWARE-LUN-03” LUN. After all VMs were unregistered, i was able to rename it back to the old “VMWARE-LUN-03” name. Then i register all the VMs on the “VMWARE-LUN-03” LUN and start them.</span></span></span>

<span class="apple-style-span"><span style="font-size: 10pt; color: black; font-family: "Verdana","sans-serif""><span style="word-spacing: 0px; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0">I checked the datastores on the other VMware ESX hosts, they were fine. As last step i changed the <span class="apple-style-span"><span style="word-spacing: 0px; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0">EnableResignature option back to 0 (off) on the VMware ESX host. </span></span></span></span></span>

<span class="apple-style-span"><span style="font-size: 10pt; color: black; font-family: "Verdana","sans-serif""><span style="word-spacing: 0px; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0"></span></span></span><span style="font-size: 10pt; font-family: "Verdana","sans-serif""></span>

<span style="word-spacing: 0px; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0"></span>

<span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><font size="+0"><span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><font color="#000000" face="TheMix B3 Light" size="3"><span class="Apple-style-span" style="word-spacing: 0px; font: 11px/17px verdana; text-transform: none; color: rgb(0,0,0); text-indent: 0px; white-space: normal; letter-spacing: normal; border-collapse: separate; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0"><span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><span class="Apple-style-span" style="word-spacing: 0px; font: 11px/17px verdana; text-transform: none; color: rgb(0,0,0); text-indent: 0px; white-space: normal; letter-spacing: normal; border-collapse: separate; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0"></span></span></span></font></span></font></span>

<span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><font size="+0"><span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><font color="#000000" face="TheMix B3 Light" size="3"><span class="Apple-style-span" style="word-spacing: 0px; font: 11px/17px verdana; text-transform: none; color: rgb(0,0,0); text-indent: 0px; white-space: normal; letter-spacing: normal; border-collapse: separate; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0"></span></font></span></font></span>

<span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><font size="+0"><span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><font color="#000000" face="TheMix B3 Light" size="3"><span class="Apple-style-span" style="word-spacing: 0px; font: 11px/17px verdana; text-transform: none; color: rgb(0,0,0); text-indent: 0px; white-space: normal; letter-spacing: normal; border-collapse: separate; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0"> <font class="" face="Courier New" style="font-family: "><font class="" face="Courier New" style="font-family: ">\[ad#verticaal\]</font></font></span></font></span></font></span>

 <span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><font size="+0"><font size="+0"><font face="TheMix B3 Light"><span class="Apple-style-span" style="word-spacing: 0px; font: 12px/14px verdana; text-transform: none; color: rgb(64,64,64); text-indent: 0px; white-space: normal; letter-spacing: normal; border-collapse: separate; text-align: left; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0"></span></font></font></font></span>

<span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><font size="+0"><font size="+0"><font face="TheMix B3 Light"></font> </font></font></span>
