---
title: "After upgrading to vCenter Server 5, &ldquo;com.vmware.converter&rdquo; alert"
date: "2012-07-23T13:33:33.000Z"
categories: 
  - "converter"
  - "vcenter-2"
tags: 
  - "converter"
  - "vcenter"
---

After upgrading to vCenter 5, the vCenter Service Status page displays the following error:

[![image](images/image_thumb8.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/07/image8.png)

com.vmware.converter alert unable to retrieve health data from https:///converter/health.xml

This error occurs because the integrated vCenter Converter plug-in is no longer available in vSphere 5!  To solve this error  following the VMware KB article listed below:

> **Error after upgrading to vCenter Server 5.0: com.vmware.converter alert unable to retrieve health data –** [**KB: 2006132**](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2006132)

After following the KB article, the  converter plug-in is removed from the vCenter Service Status page.

[![image](images/image_thumb7.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/07/image7.png)
