---
author: Ivo Beerens
categories:
- ESXi
- networking
- vSphere
date: "2013-05-01T10:12:39Z"
guid: http://www.ivobeerens.nl/?p=2264
id: 2264
ssb_fbshare_counts:
- "3"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:3;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "3"
tags:
- esxi
- networking
- vSphere
title: Test your ESXi network resiliency with ESXCLI
url: /2013/05/01/test-your-esxi-network-resiliency-with-esxcli/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

After configuring the network portion for your ESXi servers you need to test if the redundancy is working as accepted. From the ESXi layer you can bringing down/up one or more uplinks to test the network resilience. No longer you need to pull out the UTP cables. Since ESXi5 this can be done by using the **esxcli network nic down/up** command.

First log in to ESXi using for example using Tech Support Mode

- Get a overview of the installed vmnics

```
<pre lang="plain">esxcli network nic list
```

- Bring a vmnic down

```
<pre lang="plain">esxcli network nic down –n vmnicNumber
```

- Bring a vmnic up

```
<pre lang="plain">esxcli network nic up –n vmnicNumber
```

Only auto-negotiation 10Mb/100Mb/1000Mb/10000Mb speeds vmnics are supported. FlexNics with different speed are not supported.
