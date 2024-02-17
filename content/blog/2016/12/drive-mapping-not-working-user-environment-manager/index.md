---
title: "Drive mapping not working with User Environment Manager (UEM)"
date: "2016-12-21T14:25:19.000Z"
categories: 
  - "horizon"
  - "VMware"
tags: 
  - "horizon"
  - "VMware"
author: Ivo Beerens
---

> 2016-12-16 15:18:45.084 \[INFO \] Successfully mapped drive 'G:' to '\\\\filesrv-01\\apps$' ('Applicaties.xml')

When opening an elevated command prompt and type the command "_net use_", the drive mappings where displayed and accessible. The users that didn't get the drive mappings where local administrator in the Windows 10 VDI desktop.

There is a  known limitation with drive mappings if the user is:

- Local Admin
    - **and**
- User Account Control (UAC) is enabled

Changing one of them results in displaying the drive mapping in the Windows 10 VDI desktop. More information about this issue can be found here, [link](https://communities.VMware.com/message/2609027#2609027).

**Update: December 22, 2016**: Pim van de Vis ([@pimvandevis](https://twitter.com/pimvandevis)) pointed me to the following setting to solve this issue. The VMware UEM FlexEngine Advanced ADMX template has an advanced setting that is called 'Special Drive Mapping Logic'. Enabling the 'Special Drive Mapping Logic' setting solves this issues. More information can be found here, [link](https://kb.VMware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2145286).



