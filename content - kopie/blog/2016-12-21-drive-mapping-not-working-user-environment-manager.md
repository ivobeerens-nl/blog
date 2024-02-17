---
author: Ivo Beerens
categories:
- horizon
- VMware
date: "2016-12-21T15:25:19Z"
guid: http://www.ivobeerens.nl/?p=4914
id: 4914
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- horizon
- VMware
title: Drive mapping not working with User Environment Manager (UEM)
url: /2016/12/21/drive-mapping-not-working-user-environment-manager/
---

During a Horizon View implementation with User Environment Manager (UEM) 9.1 the drive mappings don’t show up for some with a Windows 10 VDI. The flexEngine log shows the drive mapping was successfully.

> 2016-12-16 15:18:45.084 \[INFO \] Successfully mapped drive ‘G:’ to ‘\\\\filesrv-01\\apps$’ (‘Applicaties.xml’)

When opening an elevated command prompt and type the command “*net use*“, the drive mappings where displayed and accessible. The users that didn’t get the drive mappings where local administrator in the Windows 10 VDI desktop.

There is a known limitation with drive mappings if the user is:

- Local Admin 
    - **and**
- User Account Control (UAC) is enabled

Changing one of them results in displaying the drive mapping in the Windows 10 VDI desktop. More information about this issue can be found here,[ link](https://communities.vmware.com/message/2609027#2609027).

**Update: December 22, 2016**: Pim van de Vis ([@pimvandevis](https://twitter.com/pimvandevis)) pointed me to the following setting to solve this issue. The VMware UEM FlexEngine Advanced ADMX template has an advanced setting that is called ‘Special Drive Mapping Logic’. Enabling the ‘Special Drive Mapping Logic’ setting solves this issues. More information can be found here, [link](https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2145286).
