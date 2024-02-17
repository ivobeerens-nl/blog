---
author: Ivo Beerens
categories:
- Uncategorized
date: "2020-10-19T22:03:19Z"
guid: https://www.ivobeerens.nl/?p=7675
id: 7675
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- in front
- RDP
- taskbar
- windows 10
title: 'Quick Tip: The local Windows 10 taskbar is in front during an RDP session'
url: /2020/10/19/quick-tip-the-local-windows-10-taskbar-is-in-front-during-an-rdp-session/
---

Sometimes it happens to me that the local taskbar of my Windows 10 laptop is in front and you don’t have access to the remote toolbar during a full-screen RDP session. This is quite annoying. In the picture below you see the local toolbar of my Windows 10 laptop is in front during a full-screen RDP session.

[![](http://localhost/wp-content/uploads/2020/10/Taskbar-300x169.png)](http://localhost/wp-content/uploads/2020/10/Taskbar.png)

Accessing the remote taskbar from the server is only possible when you don’t run RDP in full-screen mode. The fix for this is to reboot the local Windows 10 device or kill the “explorer.exe” process. You can do this manually using the Windows task manager or automated using the command line. The syntax is as follows:

\[code language=”text”\]  
C:\\Windows\\System32\\cmd.exe /c "C:\\Windows\\System32\\taskkill.exe /F /IM explorer.exe &amp; start explorer"  
```
