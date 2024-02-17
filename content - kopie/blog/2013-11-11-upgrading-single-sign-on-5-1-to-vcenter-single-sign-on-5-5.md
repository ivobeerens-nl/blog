---
author: Ivo Beerens
categories:
- sso
- vcenter
- vSphere
date: "2013-11-11T18:31:55Z"
guid: http://www.ivobeerens.nl/?p=2568
id: 2568
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- sso
- VMware
- vSphere
title: Upgrading Single Sign-On 5.1 to vCenter Single Sign-On 5.5 post task
url: /2013/11/11/upgrading-single-sign-on-5-1-to-vcenter-single-sign-on-5-5/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

With vCenter Single Sign-On (SSO) 5.5 there is no requirement for a SQL database anymore. SSO 5.5 uses a own VMware Directory Service (VMdir) database. So after the upgrade to SSO 5.5, the Single Sign-On 5.1 database and users can be removed. This is a manual process. In SQL Management Studio remove the SSO (RSA) database and the “ RSA\_DBA” and “ RSA\_USER” users created.

[![image](http://localhost/wp-content/uploads/2013/11/image_thumb.png "image")](http://localhost/wp-content/uploads/2013/11/image.png)
