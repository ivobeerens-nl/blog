---
author: Ivo Beerens
categories:
- horizon
- view
- VMware
date: "2013-02-21T15:49:43Z"
guid: http://www.ivobeerens.nl/?p=2207
id: 2207
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
title: Display the protocol used on the VMware View desktop background
url: /2013/02/21/display-the-protocol-used-on-the-vmware-view-desktop-background/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

Systinternals has a tool called “BgInfo”. With this tool it is possible to display content on a Windows desktop background. For example environment variable Information such as “computer name” and the “IP address” can be displayed. This can be very handy when testing or for people that do they support for the Windows environment.

VMware View 5.1 has the following environment variables available in a desktop session :

- ViewClient\_Broker\_DNS\_Name
- ViewClient\_Broker\_DomainName
- ViewClient\_Broker\_Remote\_IP\_Address
- ViewClient\_Broker\_Tunneled
- ViewClient\_Broker\_Tunnel\_URL
- ViewClient\_Broker\_URL
- ViewClient\_Broker\_UserName
- ViewClient\_IP\_Address
- ViewClient\_LoggedOn\_Domainname
- ViewClient\_LoggedOn\_Username
- ViewClient\_Machine\_Name
- ViewClient\_MAC\_Address
- ViewClient\_Protocol
- ViewClient\_Type
- ViewClient\_Windows\_Timezone

The View environment variables can be added to BgInfo using the custom field option.

[![image](http://localhost/wp-content/uploads/2013/02/image_thumb11.png "image")](http://localhost/wp-content/uploads/2013/02/image11.png)

After running BgInfo, the View environment variables are displayed on the desktop background. In the following example we added information on the desktop about what protocol (RDP or PCoIP) is used to connect to the View desktop:

[![image](http://localhost/wp-content/uploads/2013/02/image_thumb12.png "image")](http://localhost/wp-content/uploads/2013/02/image12.png)
