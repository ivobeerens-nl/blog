---
author: Ivo Beerens
categories:
- fusion
- office 2013
- VMware
date: "2012-09-05T22:11:05Z"
guid: http://www.ivobeerens.nl/?p=1860
id: 1860
ssb_fbshare_counts:
- "4"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:4;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "4"
tags:
- fusion
- office 2013
- VMware
title: VMware Fusion 5 and Microsoft Office 2013 screen refresh problem
url: /2012/09/05/vmware-fusion-5-and-microsoft-office-2013-screen-refresh-problem/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

When using Microsoft Office 2013 on Windows 7 or Windows 8 in VMware Fusion 5 the screen is not properly refreshed and leaving black regions.

[![image](http://localhost/wp-content/uploads/2012/09/image4_thumb.png "image")](http://localhost/wp-content/uploads/2012/09/image4.png)

This is because VMware Fusion 5 offers DirectX9 for Windows 7 and Windows 8, but Microsoft Office 2013 requires DirectX10. This is a know issue in VMware Fusion 5.

There are two work arounds available:

- Disable 3D acceleration in the VM settings
- Disable hardware acceleration in the Microsoft Office 2013 application

#### Disable 3D acceleration in the VM settings

- Shut Down the VM
- Go to Settings and click on Display
- Turn the Accelerate 3D Graphics setting to OFF

[![image](http://localhost/wp-content/uploads/2012/09/image_thumb.png "image")](http://localhost/wp-content/uploads/2012/09/image.png)

- Start the VM

#### Disable hardware acceleration in the Microsoft Office 2013 application

- Open the Office application you want to turn disable the hardware acceleration
- Click on Settings – Advanced – Disable hardware acceleration

More information can be found here.
