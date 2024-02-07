---
author: Ivo Beerens
categories:
- VMware Horizon VIew
- VMware View
date: "2014-09-17T09:15:19Z"
guid: http://www.ivobeerens.nl/?p=2842
id: 2842
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- horizon
- view
- VMware
title: Troubleshoot replication problems between VMware Horizon View Connection servers
url: /2014/09/17/vmware-view-check-the-replication-status/
---

In environments with multiple Horizon View Connection Servers (High Available) the Lightweight Directory Access Protocol (LDAP) directory is replicated. Configuration, Pool and desktop information is stored in the ADAM database. Problems with replication can result in:

- Configuration changes made are not replicated
- Authentication problems

The VMware View Administrator dashboard does not check the replication status. So regular checking the replication status is a good thing. Checking the replication status can be done by using the following command: ***repadmin.exe /showrepl localhost:389 DC=vdi,DC=vmware,DC=int***

When the replication is okay, it looks like something below:

[![image](http://localhost/wp-content/uploads/2014/06/image11_thumb.png "image")](http://localhost/wp-content/uploads/2014/06/image11.png)

When there are problems with the replication between the Connection Servers errors as “8453 Replication access was denied”, “1772 The list of RPC servers available for the binding of auto handles has been exhausted” or 8457 The destination servers is currently rejecting replication requests” are displayed using the repadmin utility.

[![3](http://localhost/wp-content/uploads/2014/06/3.png)](http://localhost/wp-content/uploads/2014/06/3.png)

When having replication problems, changes are not replicated. Here is an example when logging in the VMware View Administrator on each View Connection server, it displays differences in the ” Preparing” ” Problem Desktops” and ” Prepare for use” amounts.

| [![4](http://localhost/wp-content/uploads/2014/06/4-300x62.png)](http://localhost/wp-content/uploads/2014/06/4.png) | [![5](http://localhost/wp-content/uploads/2014/06/5-300x58.png)](http://localhost/wp-content/uploads/2014/06/5.png) |
|---|---|

**Here are some tips for troubleshooting replication problems:**

- Check if port 389 is open on the View Connection Servers
- Restart the VMware View LDAP directory service (VMware VDMS service). It will restart the View Connection Server service.

![image](http://localhost/wp-content/uploads/2014/06/image1_thumb.png "image")

- Force replication by using the following command: ***repadmin.exe /replicate fqdn-localhost:389 fqdn-remotehost:389 dc=vdi,dc=vmware,dc=int***
- *Change the fqdn-locahost and fqdn-remote host to the View Connection Server names in your environment*

[![image](http://localhost/wp-content/uploads/2014/06/image_thumb5.png "image")](http://localhost/wp-content/uploads/2014/06/image6.png)

- Ensure that replication has not been disabled by using the following command: ***repadmin /options localhost:389 -DISABLE\_OUTBOUND\_REPL -DISABLE\_INBOUND\_REPL***

With the checks listed above the replication can be checked and in most cases repaired if it is broken.
