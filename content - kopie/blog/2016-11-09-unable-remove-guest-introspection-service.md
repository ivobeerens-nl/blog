---
author: Ivo Beerens
categories:
- Uncategorized
date: "2016-11-09T12:23:39Z"
guid: http://www.ivobeerens.nl/?p=4873
id: 4873
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- NSX
- VMware
title: Unable to remove the Guest Introspection service
url: /2016/11/09/unable-remove-guest-introspection-service/
---

In my lab environment I had problems with the Guest Introspection service. The installation was failed. Trying to remove the Guest Introspection service failed every time in the Service Deployments tab.

[![2016-11-08_15h59_00](http://localhost/wp-content/uploads/2016/11/2016-11-08_15h59_00-300x93.png)](http://localhost/wp-content/uploads/2016/11/2016-11-08_15h59_00.png)

After performing the following steps, I was able to remove the Guest Introspection service :

- Put the ESXi host in maintenance mode
- Drag the ESXi host outside the cluster
- Drag the ESXi host back to the cluster
- Reboot the host
- Exit maintenance mode
- Click on resolve in the Service Deployments section

After performing these steps the Guest Introspection service is removed from the host.
