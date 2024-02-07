---
author: Ivo Beerens
categories:
- pcoip
- troubleshooting
- VMware View
date: "2013-07-26T13:21:57Z"
guid: http://www.ivobeerens.nl/?p=2397
id: 2397
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- PCoIP
- troubleshooting
- VMware View
title: Troubleshoot VMware View Security Server PCoIP port problems
url: /2013/07/26/troubleshoot-vmware-view-security-server-pcoip-port-problems/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

Recently I had to troubleshoot a VMware View Client connection problem. In a new VMware View environment the customer has installed a VMware Horizon View Security Server for the external connections. When a external View Client tried to connect through the Security Server using the PCoIP protocol to the View desktop the following appeared:

> The connection to the remote computer ended

When the users connects to the View Desktop using the LAN (without the Security Server) everything worked fine. I suspected that a PCoIP port (4172 TCP and UDP) is blocked between the Security Server and desktop pool or vice versa.

To troubleshoot this problem I used the tool “Netcat”. With Netcat TCP and UDP ports can be checked (Telnet can only check TCP ports). So I used Netcat to check the TCP and UDP ports between the Security server and View Desktop (1) and the View Desktop to the Security Server(2).

[![image](http://localhost/wp-content/uploads/2013/07/image_thumb9.png "image")](http://localhost/wp-content/uploads/2013/07/image9.png)

Here is an example how to use Netcat:

**On the View desktop run Netcat to listen to UDP port 4172**:

```
<pre lang="plain">nc –l –u –p 4172
```

**On the security server run Netcat to connect to the View Desktop on UDP port 4172**:

```
<pre lang="plain">nc –u ipaddress 4172
```

You can type some text and press enter. The text typed in the screen must be displayed on both sides, If not the port is blocked.

[![image](http://localhost/wp-content/uploads/2013/07/image_thumb10.png "image")](http://localhost/wp-content/uploads/2013/07/image10.png)

So I discovered that the 4172 UDP protocol from the View desktop pool to the Security server was blocked by a firewall. After opening this port in the firewalls the problem was solved.

More information: Netcat for Windows can be downloaded [here](http://joncraton.org/blog/netcat-for-windows).
