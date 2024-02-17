---
author: Ivo Beerens
categories:
- vcenter
- vsphere51
date: "2012-09-11T18:24:14Z"
guid: http://www.ivobeerens.nl/?p=1882
id: 1882
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- vCenter
- vsphere51
title: vCenter 5.1 Single Sign On error during installation
url: /2012/09/11/vcenter-5-1-single-sign-on-error-during-installation/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

Today vSphere 5.1 is released. I did an upgrade of my existing vSphere 5 vCenter server. During the installation of the vCenter Single Sign On (SSO) software the following warning occurred:

Error 29115: Cannot authenticate to DB.

[![image](http://localhost/wp-content/uploads/2012/09/image_thumb6.png "image")](http://localhost/wp-content/uploads/2012/09/image7.png)

After this error the installation stops and the rollback begins. To solve this make sure the **server authentication** checkbox is set to **SQL Server and Windows Authentication mode** on the SQL server.

[![image](http://localhost/wp-content/uploads/2012/09/image_thumb7.png "image")](http://localhost/wp-content/uploads/2012/09/image8.png)

Thanks to [Gabrie van Zanten](http://www.gabesvirtualworld.com/) and [Maish Saidel-Keesing](http://technodrone.blogspot.com/) for helping me out!
