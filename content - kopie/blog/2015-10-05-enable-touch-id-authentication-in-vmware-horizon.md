---
author: Ivo Beerens
categories:
- End User Computing
- VDI
- VMware View
date: "2015-10-05T08:47:43Z"
guid: http://www.ivobeerens.nl/?p=4049
id: 4049
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- vmware horizon view
title: Enable Touch ID Authentication in VMware Horizon
url: /2015/10/05/enable-touch-id-authentication-in-vmware-horizon/
---

In Horizon 6.2 it is possible to authenticate with Apples Touch ID. Touch ID is not enabled by default and has the following minimal requirements:

- iPhone 5S, 6, and 6 Plus
- iPad Air 2 and iPad mini 3
- IOS 8
- Horizon 6 version 6.2
- The View Connection Server must present a valid root-signed certificate to the Horizon Client
- Horizon 3.5 client
- The Horizon Client certificate checking mode must be set to ‘Never connect to untrusted servers or Warn before connecting to untrusted servers’

Touch ID is not enabled by default and is a global setting, so when enabling, all users are able to login using the Touch ID! There is no other way to control who can use Touch ID.

### The following steps describes enabling Touch ID

Enable BioMetrics authentication in the View Connection Server.

- Start ADSI Edit on the View Connection Server
- In the Connection Settings dialog box, select or connect to **DC=vdi,DC=vmware,DC=int**
- In the Computer pane, type **localhost**

[![0](http://localhost/wp-content/uploads/2015/10/0-300x198.png)](http://localhost/wp-content/uploads/2015/10/0.png)

- Browse to the object CN=Common, OU=Global, OU=Properties
- Edit the pae-ClientConfig attribute and add the value BioMetricsTimeout=-1 (-1 means BioMetric Authentication is supported without any time limit. To enable a time limit, enter for example 30 for 30 minutes).

[![1](http://localhost/wp-content/uploads/2015/10/1-300x199.png)](http://localhost/wp-content/uploads/2015/10/1.png) [![1a](http://localhost/wp-content/uploads/2015/10/1a-289x300.png)](http://localhost/wp-content/uploads/2015/10/1a.png)

- The new setting takes effect immediately

Horizon Client

- Check the certificate settings on the iPad or iPhone.
- Enable Touch ID in the Horizon Client and login the first time with your password.

[![IMG_7029](http://localhost/wp-content/uploads/2015/10/IMG_7029-169x300.png)](http://localhost/wp-content/uploads/2015/10/IMG_7029.png) [![IMG_7030](http://localhost/wp-content/uploads/2015/10/IMG_7030-169x300.png)](http://localhost/wp-content/uploads/2015/10/IMG_7030.png)

After that you’re been able to use the Touch ID to authenticate to the Horizon View environment. Pretty cool stuff!
