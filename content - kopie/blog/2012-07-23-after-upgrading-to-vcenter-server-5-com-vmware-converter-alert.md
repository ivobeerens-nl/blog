---
author: Ivo Beerens
categories:
- converter
- vcenter
date: "2012-07-23T15:33:33Z"
guid: http://www.ivobeerens.nl/?p=1634
id: 1634
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- converter
- vCenter
title: After upgrading to vCenter Server 5, &ldquo;com.vmware.converter&rdquo; alert
url: /2012/07/23/after-upgrading-to-vcenter-server-5-com-vmware-converter-alert/
---

After upgrading to vCenter 5, the vCenter Service Status page displays the following error:

[![image](http://localhost/wp-content/uploads/2012/07/image_thumb8.png "image")](http://localhost/wp-content/uploads/2012/07/image8.png)

```
<pre lang="plain">com.vmware.converter alert unable to retrieve health data from https://<port>/converter/health.xml</port>
```

This error occurs because the integrated vCenter Converter plug-in is no longer available in vSphere 5! To solve this error following the VMware KB article listed below:

> **Error after upgrading to vCenter Server 5.0: com.vmware.converter alert unable to retrieve health data –** [**KB: 2006132**](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2006132)

After following the KB article, the converter plug-in is removed from the vCenter Service Status page.

[![image](http://localhost/wp-content/uploads/2012/07/image_thumb7.png "image")](http://localhost/wp-content/uploads/2012/07/image7.png)
