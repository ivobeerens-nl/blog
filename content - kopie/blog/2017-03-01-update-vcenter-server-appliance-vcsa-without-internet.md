---
author: Ivo Beerens
categories:
- patch
- vcenter
- VMware
date: "2017-03-01T14:48:24Z"
guid: https://www.ivobeerens.nl/?p=4983
id: 4983
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
tags:
- patch
- vCenter
- VMware
title: Update the vCenter Server Appliance (VCSA) without internet
url: /2017/03/01/update-vcenter-server-appliance-vcsa-without-internet/
---

In this blog post I highlight how to patch or update a single vCenter Server Appliance (VCSA) without having an internet connection. The patch will be stored on a temporarily web server that is installed on a Windows machine. In this example we update the vCenter Server Appliance version from 6.0 Update 2 to 6.0 Update 3 build 5050593.

Here are the main steps:

1\. On a Windows machine install a temporarily web server to host the VCSA patch. As web server “Posh Server” ([link](http://www.poshserver.net/)) will be used. This is a small PowerShell web server. Download the Posh Server and install it on a Windows box. After the installation (use the default settings) open PowerShell (As Administrator) and execute the following commands:

```powershell  
Set-Executionpolicy unrestricted  
```

Type “y” to confirm. Go to the “*C:\\Program Files\\PoSHServer*” folder.

```powershell  
Import-Module PoSHServer  
Start-PoshServer -Port 9000  
```

The Posh web server is started and listens on port 9000

[![](http://localhost/wp-content/uploads/2017/02/PoshStart-300x182.png)](http://localhost/wp-content/uploads/2017/02/PoshStart.png)

2\. Download the patch (zip file) from the VMware website.

[![](http://localhost/wp-content/uploads/2017/03/Patch-300x205.png)](http://localhost/wp-content/uploads/2017/03/Patch.png)

Extract the patch on the Windows machine in the web server folder under “*C:\\Program Files\\PoSHServer\\webroot\\http\\update*“. Besides the patch file(ZIP), two folders are extracted (*manifest* and *package-pool*).

[![](http://localhost/wp-content/uploads/2017/02/Posh-Create-Directory-300x153.png)](http://localhost/wp-content/uploads/2017/02/Posh-Create-Directory.png)

2\. Before upgrading make sure you have a backup copy of the VCSA!

3\. Open the vCenter Server Appliance web interface (*https://VSCA-IP:5480*). Go to the update tab and click settings, select use “Specified Repository”. Enter as location of the web server and update folder. In this example we use:

```powershell  
http://IP-web-server:9000/update  
```

[![](http://localhost/wp-content/uploads/2017/02/1-1-300x181.png)](http://localhost/wp-content/uploads/2017/02/1-1.png)

Click OK, check updates and use the “Check Repository” option. (**tip**: make sure to disable the proxy configuration in the VCSA)

[![](http://localhost/wp-content/uploads/2017/02/2-1-300x161.png)](http://localhost/wp-content/uploads/2017/02/2-1.png)

The update displayed in available updates. Install the update.

[![](http://localhost/wp-content/uploads/2017/02/4-1-300x163.png)](http://localhost/wp-content/uploads/2017/02/4-1.png)

When the update is finished, click OK and reboot the appliance.

5\. After the reboot check the version and build version of the new patch.
