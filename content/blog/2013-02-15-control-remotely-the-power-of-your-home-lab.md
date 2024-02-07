---
author: Ivo Beerens
categories:
- Home Lab
- homebrew
- Whitebox
date: "2013-02-15T13:39:15Z"
guid: http://www.ivobeerens.nl/?p=2197
id: 2197
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Home Lab
- homebrew
- Whitebox
title: Control (remotely) the power of your Home Lab
url: /2013/02/15/control-remotely-the-power-of-your-home-lab/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

I have a lab at home to test for example VMware vSphere and Microsoft stuff. Running your home lab for 24/7 will result in a high electricity bill. For a couple of months I use the Internet Control Station ICS-1000 (ICS-1000) to power on my home lab when needed from **anywhere**. The ICS-1000 controls (left picture) controls the receivers (right picture). The ICS-1000 is connected to my router. In the receivers are the power cables plugged from the devices you manage.

| [![foto (2)](http://localhost/wp-content/uploads/2013/02/foto-2_thumb.jpg "foto (2)")](http://localhost/wp-content/uploads/2013/02/foto-2.jpg) | [![foto (1)](http://localhost/wp-content/uploads/2013/02/foto-1_thumb.jpg "foto (1)")](http://localhost/wp-content/uploads/2013/02/foto-1.jpg) |
|---|---|

So when needing my lab environment I open the App on my iPhone and power on the home lab from everywhere. After a short time I can remotely access the home lab and connect for example to my:

- NAS
- VMware vSphere with ESXi servers environment
- Microsoft Hyper-V environment

Using the web browser or the iPhone App for example you can program the timers to power on/off devices on specific times and dates.

| [![image](http://localhost/wp-content/uploads/2013/02/image_thumb8.png "image")](http://localhost/wp-content/uploads/2013/02/image8.png) | [![image](http://localhost/wp-content/uploads/2013/02/image_thumb9.png "image")](http://localhost/wp-content/uploads/2013/02/image9.png) |
|---|---|

I use different receivers through the whole house and control it with the ICS-1000. For example I control the light outside the house with timers I programmed in the the ICS-1000. The App has still some limitations and bugs. For example it is not possible to edit timers. To change the timers you need to delete and recreate them. Probably in March 2013 the App will be updated to solve some bugs and add new functionality.
