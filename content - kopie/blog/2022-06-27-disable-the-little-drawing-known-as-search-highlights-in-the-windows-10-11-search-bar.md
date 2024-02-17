---
author: Ivo Beerens
categories:
- Windows 10
- Windows 11
date: "2022-06-27T16:41:27Z"
guid: https://www.ivobeerens.nl/?p=8361
id: 8361
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- Search bar
- windows 10
- Windows 11
title: Disable the little drawing (known as search highlights) in the Windows 10/11
  search bar
url: /2022/06/27/disable-the-little-drawing-known-as-search-highlights-in-the-windows-10-11-search-bar/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

After deploying new Windows 10/11 images with the latest updates, Microsoft has included Search highlights. You can see if you have search highlights enabled when having a little drawing in the search bar. When clicking on the search bar it extends with graphics and more crap.

[![](http://localhost/wp-content/uploads/2022/06/1-300x181.jpg)](http://localhost/wp-content/uploads/2022/06/1.jpg)

**So what are search highlights?**

> Designed to help Windows users discover more information and related content, search highlights present noteworthy, informative, and interesting information of what’s special about each day—like holidays, anniversaries, and other moments in time both globally and in your region

This new feature can be nice for home users but not for most enterprise environments. So I disable this feature for all the Windows 10/11 deployments.

**Disable search highlights by using a Group Policy Object (GPO)**

- Make sure you have at least the Administrative Templates (admx) for Windows 10 November 2021 Update (21H2) – **v2.0** ([**link**](https://www.microsoft.com/en-us/download/details.aspx?id=104042)).
- Copy the ADMX files to the Group Policy Central Store in the sysvol folder (example: **\\\\<fqd domain name>\\SYSVOL\\<fqd domain name>\\policies\\PolicyDefinitions**)
- Create or edit a Group Policy Object (GPO) to the OU where the computer objects are placed
- Browse to Computer Configuration – Policies – Administrative Templates – Windows Components – Search
- Open the “Allow search highlights” setting and select Disable
- Perform a “gpupdate /force” on the Windows client

[![](http://localhost/wp-content/uploads/2022/06/2-300x276.jpg)](http://localhost/wp-content/uploads/2022/06/2.jpg)

**Disable search highlights by registry setting**

Another method is by creating a registry key on the Windows 10/11 machine.

- Execute the following command as administrator:

```powershell  
REG ADD "HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\Windows Search" /v "EnableDynamicContentInWSB" /t REG\_DWORD /d "0" /f  
```

Disabling this setting turns off search highlights in the taskbar search box and in search home.
