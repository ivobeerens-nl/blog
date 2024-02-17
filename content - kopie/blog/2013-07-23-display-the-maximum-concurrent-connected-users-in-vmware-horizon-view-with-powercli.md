---
author: Ivo Beerens
categories:
- horizon
- PowerCLI
- view
date: "2013-07-23T11:37:33Z"
guid: http://www.ivobeerens.nl/?p=2392
id: 2392
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- PowerCLI
- vmware horizon view
title: Display the maximum concurrent connected users in VMware Horizon View with
  PowerCLI
url: /2013/07/23/display-the-maximum-concurrent-connected-users-in-vmware-horizon-view-with-powercli/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

VMware Horizon View generates everyday at 5 minutes for midnight an event how many concurrent users connected to View that day. This information can be useful for example when when investing trends.

When the Event database in the VMware Horizon View Administrator is configured, this information can be found using the VMware Horizon View Administrator, Monitoring, select Events and filter for “over the past”

[![image](http://localhost/wp-content/uploads/2013/07/image_thumb6.png "image")](http://localhost/wp-content/uploads/2013/07/image6.png)

With PowerCLI the daily maximum concurrent connected users can be displayed by using the following command from the VMware View Connection server using View PowerCLI:

```
<pre lang="plain">Get-EventReport -viewName user_count_events
```

[![image](http://localhost/wp-content/uploads/2013/07/image_thumb7.png "image")](http://localhost/wp-content/uploads/2013/07/image7.png)

 The following command displays the concurrent users from the last 5 days:

```
<pre lang="plain">Get-EventReport -viewName user_count_events -startDate ((Get-Date).AddDays(-5)) | sort time | Select Time,Usercount
```

[![image](http://localhost/wp-content/uploads/2013/07/image_thumb8.png "image")](http://localhost/wp-content/uploads/2013/07/image8.png)

You can customize the command further for your needs.
