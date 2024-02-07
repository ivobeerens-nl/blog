---
author: Ivo Beerens
categories:
- VMware
- vSphere
date: "2019-04-24T09:02:21Z"
enclosure:
guid: https://www.ivobeerens.nl/?p=6846
id: 6846
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- vCenter Server
- vcsa
- VMware
title: Blue circle in the vSphere client after upgrading to vCenter Server 6.7 Update
  2
url: /2019/04/24/blue-circle-in-the-vsphere-client-after-upgrading-to-vcenter-server-6-7-update-2/
---

After upgrading the vCenter Server Appliance (VCSA) to version 6.7 Update 2, I tried to log in using the vSphere Client. After entering the credentials an endless blue running circle appears.

[![](http://localhost/wp-content/uploads/2019/04/vcsaup2-300x161.png)](http://localhost/wp-content/uploads/2019/04/vcsaup2.png)

<div class="wp-video" style="width: 1200px;"><video class="wp-video-shortcode" controls="controls" height="643" id="video-6846-1" preload="metadata" width="1200"><source src="http://localhost/wp-content/uploads/2019/04/vcsaup2.mp4?_=1" type="video/mp4"></source><http://localhost/wp-content/uploads/2019/04/vcsaup2.mp4></video></div>In the VAMI interface (https://vcsa-fqdn:5480) of the VCSA, the health statistics of all the components are green (okay) so I decided to reboot the VCSA.

After the VCSA reboot I encountered the same blue running circle when trying to log in using the vSphere Client. I tried Firefox and Google and the Internet Explorer browser. The only browser that worked was Internet Explorer. I never used Internet Explorer before so I tried to clear the cache of Google Chrome and Firefox using the following methods:

Clear cache, cookies and history of Google Chrome:

- Open Chrome.
- At the top right, click More ![More](https://storage.googleapis.com/support-kms-prod/ArAlBcUAe8h1l5m69uxnwElxkqwW0QdtIc3F)
- Click More tools and then Clear browsing data
- Time range: All time
- Select Browser history, cookies and cache images and files
- Click Clear data

Clear cache and cookies of Firefox browser:

- Open firefox
- In the address bar enter: about:preferences
- Click Privacy &amp; Security
- Under Cookies and Site Data select Clear Data
- Check Cookies and Site Data and Cached Web Content
- Click Clear and select Clear Now

After clearing the cache I was able to log in using the vSphere Client without the endless blue circle. So make sure to clear the cache of the browser(s) when experiencing the circle problem.
