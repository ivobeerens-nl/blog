---
author: Ivo Beerens
categories:
- windows server 2012
date: "2013-01-02T15:16:11Z"
guid: http://www.ivobeerens.nl/?p=2106
id: 2106
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:2;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
tags:
- windows server 2012
title: License Windows Server 2012 editions in virtual environments
url: /2013/01/02/license-windows-server-2012-editions-in-virtual-environments/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

As virtualization consultant I got frequently questions about Windows Server 2012 licensing in virtual environments such as VMware and Hyper-V. Here is a short blog about Windows Server 2012 licensing in virtual environments.

What about the Windows Server 2012 license:

- The Windows Server 2012 licenses are based on the physical processor
- A single license covers two physical processors.

There are two license editions available:

- **Windows Server 2012 Standard edition.** A Standard edition license will entitle you to run up to two VMs on up to two processors.
- **Windows Server 2012 Datacenter edition**. A Datacenter edition license will entitle you to run an unlimited number of VMs on up to two processors

The only difference between the two editions are the virtualization rights. All the features that are available, are the same in both editions for example Windows Server Failover Clustering! The Enterprise edition is retired in Windows Server 2012 licensing.

Windows Server 2012 license examples:

- For a 2 processor VMware or Hyper-V host with 8 VM’s you need 4 Standard edition licenses
- For a 4 processor VMware or Hyper-V host with 4 VM’s you need 2 Standard edition licenses

The retail list prices of Windows Server 2012 are:

| **Edition** | **Retail list price ($)** |
|---|---|
| Standard | 882 |
| Datacenter | 4809 |

Client Access Licenses (CALs) will be needed to access to Windows Server 2012 servers.

The decision to use the standard of datacenter edition licensing depends on the total number of VMs on your hosts. On hosts with more than 11 VMs the datacenter license will be cost effective.

It is allowed to reassign a Windows Server 2012 license from one server to another server but more often than every 90 days. There are some expectations of the 90 days rule to assign the license sooner for example:

- When having a permanent hardware failure
- Reallocate processors from one host to another

**What about moving a VM?**

When using a dynamic move a Windows Server VM to another node for example with Windows Server Clustering, VMware vMotion or Live Migration, the other node needs to be have sufficient Microsoft Windows Server 2012 licenses. So in most cases an Windows Server 2012 Datacenter edition license is recommend.
