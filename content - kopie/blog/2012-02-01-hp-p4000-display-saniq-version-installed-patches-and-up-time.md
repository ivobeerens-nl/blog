---
author: Ivo Beerens
categories:
- hp
- lefthand
- p4000
date: "2012-02-01T16:45:47Z"
guid: http://www.ivobeerens.nl/?p=1263
id: 1263
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hp
- lefthand
- p4000
title: Display HP P4000 SAN/iQ version, installed patches and up-time
url: /2012/02/01/hp-p4000-display-saniq-version-installed-patches-and-up-time/
---

<font color="#000000">During a health check I needed to know the SAN/iQ version, installed patches and the up-time of the HP P4000 storage nodes because of a nasty bug in SAN/iQ 9.0 or 9.0.01 that hang or reboot nodes after 208.5 days (More information about the bug can be found in the HP Customer Advisory found </font><font color="#000000">**here**</font><font color="#000000">)</font>

<font color="#000000">To see the SAN/iQ version, installed patches and the up-time (thanks to Calvin Zito @HPStorageGuy for guiding me to the up-time counter in CMC) </font>

<font color="#000000"> </font>

<font color="#000000">Here are the steps:</font>

<font color="#000000"></font>

<font color="#000000">**1**. Open the Centralized Management Console (CMC)</font>

<font color="#000000">**2**. Login</font>

<font color="#000000">**3**. Expand the cluster</font>

<font color="#000000">**4**. Expand the Storage Systems </font>

<font color="#000000">**5.** Select Diagnostics for the first node (**1**)</font>

<font color="#000000">**6**. Select “Hardware information” (**2**)</font>

<font color="#000000">**7**. Select “Click to refresh” (**3**) </font>

[<font color="#000000">[![image](http://localhost/wp-content/uploads/2012/02/image_thumb3.png "image")](http://localhost/wp-content/uploads/2012/02/image3.png)</font>](http://localhost/wp-content/uploads/2012/02/image.png)

<font color="#000000">**8**. The Storage System Software displays the SAN/iQ version and Software Patches installed:</font>

[<font color="#000000">[![image](http://localhost/wp-content/uploads/2012/02/image6_thumb.png "image")](http://localhost/wp-content/uploads/2012/02/image6.png)</font>](http://localhost/wp-content/uploads/2012/02/image1.png)

<font color="#000000"></font>

<font color="#000000">**9**. Scroll down to the Stat section and look at the Machine Uptime. The up-time is in hours, 2138/24= 89 days up-time for one node.</font>

[<font color="#000000">[![image](http://localhost/wp-content/uploads/2012/02/image10_thumb.png "image")](http://localhost/wp-content/uploads/2012/02/image10.png)</font>](http://localhost/wp-content/uploads/2012/02/image2.png)

<font color="#000000">**10**. Repeat step 5 till 9 for all storage nodes</font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"> </font>

\[ad#banner\]

<font color="#000000"></font>
