---
author: Ivo Beerens
categories:
- Uncategorized
date: "2016-07-26T21:16:15Z"
guid: http://www.ivobeerens.nl/?p=4555
id: 4555
ssb_fbshare_counts:
- "4"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:4;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "4"
tags:
- VMware Horizon
title: Slow logoff from a Horizon View VDI desktop
url: /2016/07/26/slow-logoff-horizon-view-vdi-desktop/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

When building a new Horizon Environment, the logoff and refresh maintenance window takes a couple of minutes.

When a user is logging off from a Horizon VDI session the desktop refreshed in a floating pool. (A refresh action can be configured per pool). During the logoff and refresh window the desktop is in “maintenance mode” and the user is unable log in.

The following warning is displayed in the Horizon View Client when trying to connect:

> The View Agent reports that this desktop is currently logging off a previous session. Please try again later.

[![1](http://localhost/wp-content/uploads/2016/07/1-1-300x210.png)](http://localhost/wp-content/uploads/2016/07/1-1.png)

The new installed Horizon environment has the following products and versions installed:

- VMware vSphere 6.x
- Virtual SAN 6.2
- Horizon 7
- App Volumes 2.10
- User Environment Manager 9.0
- Sophos Antivirus for vShield
- Windows 7 desktop
- Windows 2012 RDS

After some troubleshooting, I disabled the “Sophos Antivirus for vShield” appliance per ESXi server. After disabling the appliance the VDI desktop logoff and refresh window was finished in a couple of seconds instead of a couple of minutes. So the problem has something to do with the virusscanner or vShield Endpoint. After digging deeper it was VMware Tools related. In April 2016 VMware Tools 10.0.8 was released that fixes performance problems with NSX and VMware vCloud Networking and Security 5.5.x.

After upgrading the VMware Tools version to 10.0.8 in the golden image the slow logoff and refresh was solved. Within a couple of seconds the user is now able to log off again to a fresh new VDI desktop.

More information on VMware Tools 10.0.8: [Link](https://pubs.vmware.com/Release_Notes/en/vmwaretools/1008/vmware-tools-1008-release-notes.html).
