---
author: Ivo Beerens
categories:
- VMware
- vshield
date: "2013-12-18T09:55:26Z"
guid: http://www.ivobeerens.nl/?p=2606
id: 2606
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:2;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
tags:
- VMware
- vshield
title: vCloud Networking and Security license in Evaluation Mode
url: /2013/12/18/vcloud-networking-and-security-license-in-evaluation-mode/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

A customer has a VMware vSphere 5.1 environment with VMware Horizon View 5.2 environment and Trend Micro Deep Security installed. Trend Micro Deep Security uses the VMware vShield Endpoint framework. In the vSphere license manager asset the “vCloud Networking and Security” license is displayed in evaluation mode and has a expire date.

[![image](http://localhost/wp-content/uploads/2013/12/image_thumb5.png "image")](http://localhost/wp-content/uploads/2013/12/image5.png)

This is strange because vSphere 5.1 > includes a vShield Endpoint license. So no extra vShield licenses are required. I found a [KB](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2036875) about vShield Endpoint. It states:

> The vShield Endpoint asset may show up as unlicensed or with an evaluation license in the vCenter Server console, but functionality is fully enabled.

So you don’t have to worry that vShield Endpoint stops working. This is by design and will probably fixed in a later version.
