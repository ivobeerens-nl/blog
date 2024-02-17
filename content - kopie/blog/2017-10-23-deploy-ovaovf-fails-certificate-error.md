---
author: Ivo Beerens
categories:
- vSphere
date: "2017-10-23T22:42:55Z"
guid: https://www.ivobeerens.nl/?p=5264
id: 5264
ssb_fbshare_counts:
- "3"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "3"
tags:
- vCenter
- VMware
title: Deploy an OVA/OVF fails with certificate error
url: /2017/10/23/deploy-ovaovf-fails-certificate-error/
---

When trying to deploy an OVA/OVF with the vSphere Web Client the following error is displayed:

> The operation failed for an undetermined reason. Typically this problem occurs due to certificates that the browser does not trust. If you are using self-signed or custom certificates, open the URL below in a new browser tab and accept the certificate, then retry the operation.

[![](http://localhost/wp-content/uploads/2017/10/error-300x174.jpg)](http://localhost/wp-content/uploads/2017/10/error.jpg)

This error occurs with vSphere 6.5 because the certificates are not trusted. The self-signed certificates are used and are not added to the trusted root certification store.

To deploy a OVF/OVA to the vCenter Server appliance trusted root CA must be added to the certificate store. The following steps will work with Chrome and Internet Explorer:

- Open the vCenter URL: *https://vcenter-FQDN*

[![](http://localhost/wp-content/uploads/2017/10/2-300x137.jpg)](http://localhost/wp-content/uploads/2017/10/2.jpg)

- Select the “Download trusted root CA certificates” and save the archive(ZIP) file
- Extract the archive (ZIP)

[![](http://localhost/wp-content/uploads/2017/10/6-300x66.jpg)](http://localhost/wp-content/uploads/2017/10/6.jpg)

- Start – Run – MMC
- File – Add Snap-ins – Certificates – Computer Account – Local computer
- Open Trusted Root Certification Authories – Certificates
- Import the two \*.crt certificates

[![](http://localhost/wp-content/uploads/2017/10/5-300x145.jpg)](http://localhost/wp-content/uploads/2017/10/5.jpg)

- Close the browser and re-open the browser and navigate to the vCenter Server using the FQDN.
- Now the URL is marked as secure (green lock) and you’re able to import the OVA/OVF

[![](http://localhost/wp-content/uploads/2017/10/Green-300x153.jpg)](http://localhost/wp-content/uploads/2017/10/Green.jpg)
