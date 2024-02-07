---
author: Ivo Beerens
categories:
- vCAC
- vCloud Automation Center
- VMware
date: "2014-04-23T11:58:09Z"
guid: http://www.ivobeerens.nl/?p=2770
id: 2770
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- vCAC
- vCloud Automation Center
- VMware
title: Update the vCenter inventory in vCAC manually
url: /2014/04/23/update-the-vcenter-inventory-in-vcac-manually/
---

When creating a new template in vCenter and want to use the new created template in a blueprint, the blueprint will not list the template because the vCenter inventory isn’t updated in vCAC. By default vCAC will update the vCenter inventory once a day. To manually update the vCenter inventory in vCAC 6.x use the following steps:

- Login the vCloud Automation Center console
- Select the Infrastructure tab
- Select Compute Resources
- Select the Compute Resource you want to update. In this example it’s “cluster-01”
- Select “Data Collection”

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb7.png "image")](http://localhost/wp-content/uploads/2014/04/image7.png)

- Click on the “Request Now” button in the Inventory field update the vCenter inventory.
- Wait till the vCAC page refeshes and check the last completed and status field to be sure that the refresh succeeded.

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb8.png "image")](http://localhost/wp-content/uploads/2014/04/image8.png)

- Creating a new blueprint will list the new created template in vCenter
