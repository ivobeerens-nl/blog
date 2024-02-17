---
author: Ivo Beerens
categories:
- power
- PowerCLI
- view
- VMware
date: "2014-01-22T22:32:53Z"
guid: http://www.ivobeerens.nl/?p=2653
id: 2653
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- horizon
- PowerCLI
- VMware View
title: Display VMware Horizon View Pool information using PowerCLI
url: /2014/01/22/display-vmware-horizon-view-pool-information-using-powercli/
---

For a VMware View Horizon Healthcheck I needed to display all VMware View Pools created and export some settings for documentation. The easiest way to do this is using View PowerCLI on a VMware View Connection server.

Here are some examples to use:

Display all the pools and settings:

```
<pre lang="plain">get-pool
```

Display the pools with selected fields in table form:

```
<pre lang="plain">Get-pool | select DisplayName,Pool_ID,Enabled,MinimumCount,MaximumCount,HeadroomCount,Persistence,Pooltype,Protocol | FT -AutoSize
```

[![image](http://localhost/wp-content/uploads/2014/01/image_thumb1.png "image")](http://localhost/wp-content/uploads/2014/01/image1.png)

Display the some fields in table form and export the pool information to a a text file:

```
<pre lang="plain">get-pool | select DisplayName,Pool_ID,Enabled,MinimumCount,MaximumCount,HeadroomCount,Persistence,Pooltype,Protocol | FT -AutoSize | out-file c:\temp\pools.txt
```

The get-pool commands does not export all the settings that can be provided in a VMware View pool.
