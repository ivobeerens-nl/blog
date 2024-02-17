---
title: "Update the vCenter Server Appliance (VCSA) without internet"
date: "2017-03-01T13:48:24.000Z"
categories: 
  - "patch"
  - "vcenter-2"
  - "VMware"
tags: 
  - "patch"
  - "vcenter"
  - "VMware"
author: Ivo Beerens
---

Here are the main steps:

1\. On a Windows machine install a temporarily web server to host the VCSA patch.  As web server "Posh Server" ([link](http://www.poshserver.net/)) will be used. This is a small PowerShell web server. Download the Posh Server and install it on a Windows box. After the installation (use the default settings) open PowerShell (As Administrator) and execute the following commands:

\[code language="PowerShell"\] Set-Executionpolicy unrestricted \[/code\]

Type "y" to confirm. Go to the "_C:\\Program Files\\PoSHServer_" folder.

\[code language="PowerShell"\] Import-Module PoSHServer Start-PoshServer -Port 9000 \[/code\]

The Posh web server is started and listens on port 9000

[![](images/PoshStart-300x182.png)](images/PoshStart.png)

2\. Download the patch (zip file)  from the VMware website.

[![](images/Patch-300x205.png)](images/Patch.png)

Extract the patch on the Windows machine in the web server folder under "_C:\\Program Files\\PoSHServer\\webroot\\http\\update_". Besides the patch file(ZIP), two folders are extracted (_manifest_ and _package-pool_).

[![](images/Posh-Create-Directory-300x153.png)](images/Posh-Create-Directory.png)

2. Before upgrading make sure you have a backup copy of the VCSA!

3\. Open the vCenter Server Appliance web interface (_https://VSCA-IP:5480_). Go to the update tab and click settings, select use "Specified Repository". Enter as location of the web server and update folder. In this example we use:

\[code language="PowerShell"\] http://IP-web-server:9000/update \[/code\]

[![](images/1-1-300x181.png)](images/1-1.png)

Click OK, check updates and use the "Check Repository" option. (**tip**: make sure to disable the proxy configuration in the VCSA)

[![](images/2-1-300x161.png)](images/2-1.png)

The update displayed in available updates. Install the update.

[![](images/4-1-300x163.png)](images/4-1.png)

When the update is finished, click OK and reboot the appliance.

5\. After the reboot check the version and build version of the new patch.



