---
author: Ivo Beerens
categories:
- Uncategorized
date: "2018-09-12T16:23:45Z"
firstpublish:
- "1"
guid: https://www.ivobeerens.nl/?p=6186
id: 6186
image: /wp-content/uploads/2018/09/error.png
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- VMware
title: vCenter Server Appliance (VCSA) Failed to send http data error
url: /2018/09/12/vcenter-server-appliance-vcsa-failed-to-send-http-data-error/
---

When trying to upgrade the vCenter Server Appliance (VCSA) to version 6.7 using the GUI wizard, I’ve got the following error:

[![](http://localhost/wp-content/uploads/2018/09/error-300x58.png)](http://localhost/wp-content/uploads/2018/09/error.png)

> Failed to send http data.

I checked the logs but didn’t find any clue. When installing the VCSA using the CLI I’ve got the same “Failed to send http data” error ([link](http://localhost/2018/08/20/vcenter-server-appliance-vcsa-automated-unattended-deployment/)). The FQDN of the ESXi host was revolvable by DNS and reverse lookup worked. After changing the ESXi FQDN to the IP address of the ESXi host, the deployment finished without errors. I changed the “ESXi host or vCenter Server name” in the wizard step 3 and 4 to fix the problem.

[![](http://localhost/wp-content/uploads/2018/09/failed-to-send-1-300x153.png)](http://localhost/wp-content/uploads/2018/09/failed-to-send-1.png) [![](http://localhost/wp-content/uploads/2018/09/failed-to-send-300x153.png)](http://localhost/wp-content/uploads/2018/09/failed-to-send.png)

I couldn’t find what causes the “Failed to send http data” error. I had this error during installs and upgrades in different environments. Hopefully someone can explain what happen or it is a bug that will be solved in future releases.
