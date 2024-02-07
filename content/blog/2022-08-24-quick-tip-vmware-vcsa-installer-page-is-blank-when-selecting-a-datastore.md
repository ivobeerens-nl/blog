---
author: Ivo Beerens
categories:
- vSphere
date: "2022-08-24T14:40:06Z"
guid: https://www.ivobeerens.nl/?p=8414
id: 8414
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- upgrade
- VMware
- vSphere
title: 'Quick tip: VMware VCSA installer page is blank when selecting a datastore'
url: /2022/08/24/quick-tip-vmware-vcsa-installer-page-is-blank-when-selecting-a-datastore/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

While upgrading a vCenter Server 6.7 to version 7 Update 3 using the vCenter Server 7 UI installer, I was not able to select a datastore for installing the new vCenter Server Appliance (VCSA).

The datastore selection was blank as shown in the following image.

[![](http://localhost/wp-content/uploads/2022/08/1.jpg) ](http://localhost/wp-content/uploads/2022/08/1.jpg)

After googling I found the solution on a blog from another vExpert ([link](https://arabitnetwork.com/2019/03/10/vcsa-6-5-6-7-ui-installer-opens-a-blank-page/)) who experience this issue with VCSA 6.5/6.7 installers. So the issue still exists in the vCenter Server 7 UI installer.

Here are the steps to solve this:

- Go to the %appdata% folder (it opens the C:\\Users\\<username>\\AppData\\Roaming folder)
- Delete the installer folder.
- Run the VCSA installer again and you see the datastores again
