---
author: Ivo Beerens
categories:
- vcenter
date: "2018-02-13T21:57:21Z"
guid: https://www.ivobeerens.nl/?p=5446
id: 5446
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- certificate
- vCenter
- vcsa
title: Firefox does not trusts vCenter signed CA certificates
url: /2018/02/13/firefox-not-trusts-vcenter-ca-signed-certificates/
---

For a vCenter Server environment I replaced the default SSL certificates with CA signed SSL certificates. The Platform Service Controller (PSC) is configured as VMCA subordinate CA. When opening the vSphere Web/HTML5 Client, Firefox displays the following warning: *Your connection is not secure*.

[![](http://localhost/wp-content/uploads/2018/02/insecure-300x257.png)](http://localhost/wp-content/uploads/2018/02/insecure.png)

This is because Firefox does not trust root certificates in the Windows certificate store. Since Firefox 49 a new option is included which allows Firefox to trust root certificates. This option is not enabled by default.

The following steps illustrate how to configure Firefox to use the Windows certificate store:

- Open Firefox
- In the address bar type: *about:config*
- Accept the warning
- Navigate to Preference name: *security.enterprise\_roots.enabled*
- Set the value to: *true*

[![](http://localhost/wp-content/uploads/2018/02/security-300x210.png)](http://localhost/wp-content/uploads/2018/02/security.png)

Firefox now trust the root certificates in the Windows certificate store.

[![](http://localhost/wp-content/uploads/2018/02/secure-300x173.png)](http://localhost/wp-content/uploads/2018/02/secure.png)
