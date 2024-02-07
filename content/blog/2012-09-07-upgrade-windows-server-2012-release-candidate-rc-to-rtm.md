---
author: Ivo Beerens
categories:
- upgrade
- windows server 2012
date: "2012-09-07T11:06:24Z"
guid: http://www.ivobeerens.nl/?p=1873
id: 1873
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- upgrade
- windows server 2012
title: Upgrade Windows Server 2012 Release Candidate (RC) to RTM
url: /2012/09/07/upgrade-windows-server-2012-release-candidate-rc-to-rtm/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

Now Windows Server 2012 is release I tried to upgrade my lab environment from Microsoft Windows Server 2012 RC 8400 to Windows 2012 RTM. It is not officially supported to upgrade from Windows Server 2012 RC to Windows Server 2012 RTM by Microsoft.

I did the following steps to upgrade:

- Downloaded the Windows Server 2012 ISO
- Mount or extract the ISO
- Executed setup.exe
- After several screens it is possible to choose for “**Upgrade: Install Windows and keep files, settings and applications**” option

[![image](http://localhost/wp-content/uploads/2012/09/image_thumb1.png "image")](http://localhost/wp-content/uploads/2012/09/image1.png)

- Now the he following error appeared:

> The upgrade cannot continue. The upgrade you needs to be running the following Windows Server 2012 build number of higher: 8508.0

[![image](http://localhost/wp-content/uploads/2012/09/image_thumb2.png "image")](http://localhost/wp-content/uploads/2012/09/image2.png)

- use the work around by editing the file “cversion.ini” found in the “sources” folder. Change the “**MinServer=8508.0**” line in “**MinServer=8400.0**”

[![image](http://localhost/wp-content/uploads/2012/09/image_thumb3.png "image")](http://localhost/wp-content/uploads/2012/09/image3.png)

- Start the setup process again. Now repeat the above steps. The installation checks the compatibility. In my case the following errors are displayed:

[![image](http://localhost/wp-content/uploads/2012/09/image_thumb4.png "image")](http://localhost/wp-content/uploads/2012/09/image5.png)

- To solve the above errors I did the following things:

> – Uninstall the Intel Wired PROset for Windows software
> 
> – Because the Active Directory (AD) role is installed, I needed to upgrade the AD schema by using the ADPREP /FORESTPREP and ADPREP / DOMAINPREP commands
> 
> – Reboot the system

- Again the setup process must be started and the upgrades completes. After the upgrade the Windows Server 2012 version is Build 9200 (RTM).

[![image](http://localhost/wp-content/uploads/2012/09/image_thumb5.png "image")](http://localhost/wp-content/uploads/2012/09/image6.png)
