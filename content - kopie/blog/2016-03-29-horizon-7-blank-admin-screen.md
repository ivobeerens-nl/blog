---
author: Ivo Beerens
categories:
- horizon
- VMware
date: "2016-03-29T08:29:05Z"
guid: http://www.ivobeerens.nl/?p=4367
id: 4367
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- horizon
- view
- VMware
title: Horizon View Administrator displays a blank error window
url: /2016/03/29/horizon-7-blank-admin-screen/
---

After upgrading to VMware Horizon View 7, the administrator webpage displays a blank error window when trying to connect using the IP address of the Connection Server.

[![blank](http://localhost/wp-content/uploads/2016/03/blank-300x125.png)](http://localhost/wp-content/uploads/2016/03/blank.png)

Horizon View 7 adds new security features that checks for the original URL for the web request. If not, it rejects the request and display the blank error window.

Steps to resolve this:

- Use **https://FQDN/admin**

**or**

- On every Connection Server create a **locked.properties** text file in **c:\\Program Files\\VMware\\VMware View\\Server\\sslgateway\\conf**
- Add the following line: 
    - **checkOrigin=false**

[![locked](http://localhost/wp-content/uploads/2016/03/locked-300x169.png)](http://localhost/wp-content/uploads/2016/03/locked.png)

- Save the file
- Restart the “VMware Horizon View Connection Server” service

After the modification you’re able to connect to the View Administrator URL using the IP address of the Connection Server.

[![4](http://localhost/wp-content/uploads/2016/03/4-300x207.png)](http://localhost/wp-content/uploads/2016/03/4.png)
