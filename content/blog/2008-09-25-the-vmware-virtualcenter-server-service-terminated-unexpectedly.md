---
aktt_notify_twitter:
- "no"
author: Ivo Beerens
categories:
- ESX
- VirtualCenter
- VMware
date: "2008-09-25T15:24:09Z"
guid: http://www.ivobeerens.nl/?p=128
id: 128
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Error
- VirtualCenter
- VMware
title: The VMware VirtualCenter Server service terminated unexpectedly
url: /2008/09/25/the-vmware-virtualcenter-server-service-terminated-unexpectedly/
---

After rebooting the VMware VirtualCenter (VC) server, i was unable to logon using the VI-client in VC. In the Windows event log the following Error is listed:

> Event Type: Error  
> Event Source: Service Control Manager  
> Event Category: None  
> Event ID: 7031  
> Date: 25-9-2008  
> Time: 13:39:58  
> User: N/A  
> Computer: VC1  
> Description:  
> The VMware VirtualCenter Server service terminated unexpectedly. It has done this 1 time(s). The following corrective action will be taken in 300000 milliseconds: Restart the service.
> 
> For more information, see Help and Support Center at http://go.microsoft.com/fwlink/events.asp.

It seems that the VC server service is started before the SQL 2005 service is started. The solution is the delay the VirtualCenter service from starting till the Microsoft SQL 2005 service is started. Microsoft has a KB article “[How to delay loading of specific services”.](http://support.microsoft.com/kb/193888)

I did the following:

Open the regedit.exe and browse to the HKLM\\SYSTEM\\CurrentControlSet\\Services\\**MSSQLSERVER** (for MS SQL 2005 standard). So you know the name of the service.

[![image](http://localhost/wp-content/uploads/2008/10/image-thumb.png)](http://localhost/wp-content/uploads/2008/10/image.png)

Browse to HKLM\\SYSTEM\\CurrentControlSet\\Services\\vpxd and open the DependOnService property

[![image](http://localhost/wp-content/uploads/2008/10/image-thumb1.png)](http://localhost/wp-content/uploads/2008/10/image1.png)

Add the name MSSQLSERVER to this multi-string. **Ensure that the last line is empty**.

[![image](http://localhost/wp-content/uploads/2008/10/image-thumb2.png)](http://localhost/wp-content/uploads/2008/10/image2.png)

Close the Registry Editor and restart the VirtualCenter server and test if it VMware VirtualCenter service starts.

<span style="font-family: Courier New;">\[ad#verticaal\]</span>
