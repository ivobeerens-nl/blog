---
author: Ivo Beerens
categories:
- Uncategorized
date: "2019-12-12T12:21:19Z"
guid: https://www.ivobeerens.nl/?p=7225
id: 7225
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- VMware
- VMware Horizon
title: Export VMware Horizon pool settings
url: /2019/12/12/export-vmware-horizon-pool-settings/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

I created a simple PowerShell script that exports all the pool settings on a Horizon Connection Server and saves them in a separate JSON file. To run this script follow the requirements below:

- Download the Export-pools.ps1 script from my [GitHub](https://github.com/ibeerens/VMware-Horizon) page.
- Edit the script script and enter the correct file location in the ‘$fileloc’ variable. The default file location is c:\\temp
- Download the VMware.Hv.Helper module ([link](https://github.com/vmware/PowerCLI-Example-Scripts))
- Copy the VMware.Hv.Helper module to the module location. Use the ‘$env:PSModulePath’ PowerShell command to list the module path(s)
- Run the ‘Export-HorPool.ps1’ script in PowerShell

[![](http://localhost/wp-content/uploads/2019/12/1-1-300x29.png)](http://localhost/wp-content/uploads/2019/12/1-1.png)

After the ‘Export-HorPool.ps1’ scrript has run all the pool settings are exported to a JSON file.

[![](http://localhost/wp-content/uploads/2019/12/2-300x172.png)](http://localhost/wp-content/uploads/2019/12/2.png)
