---
author: Ivo Beerens
categories:
- Uncategorized
date: "2016-01-13T20:05:05Z"
guid: http://www.ivobeerens.nl/?p=4176
id: 4176
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
title: Unable to pair the broker agent with the Horizon adapter in vROps
url: /2016/01/13/vrealize-operations-manager/
---

When trying to pair the Broker agent 6.2 with the Horizon adapter in vRealize Operations Manager (vROps), it fails with the following error:

> Could not Pair with Adapter Address …. An Error has Occurred. Failed to pair the Adapter. Operation Adapter Pairing Failed.

[![1](http://localhost/wp-content/uploads/2016/01/1-300x224.png)](http://localhost/wp-content/uploads/2016/01/1.png)

This issue occurs when the firewall rules on the vRealize Operations Manager are incorrect. To resolve this issue update the firewall rules using the following steps:

- Open the VM console of the vRealize Operations Appliance or enable SSH (l[ink](http://localhost/2015/12/08/4105/))
- Log in as root user/
- Open the “/opt/vmware/etc/vmware-vcops-firewall.conf” file in vi
- Make sure the following entries are added to the V4V Adapter specific ports section

<span style="font-family: 'Courier New';">\# v4V Adapter specific ports  
TCPPORTS=”$TCPPORTS 3091:3095″  
TCPPORTS=”$TCPPORTS 3099:3101″</span>

[![2](http://localhost/wp-content/uploads/2016/01/2-300x38.png)](http://localhost/wp-content/uploads/2016/01/2.png)

- Save the file
- Restart the firewall by using the following command:

<span style="font-family: 'Courier New';">/etc/init.d/vmware-vcops-firewall restart</span>

Try to pair the adapter again. The pairing must now be successful.

[![3](http://localhost/wp-content/uploads/2016/01/3-300x223.png)](http://localhost/wp-content/uploads/2016/01/3.png)
