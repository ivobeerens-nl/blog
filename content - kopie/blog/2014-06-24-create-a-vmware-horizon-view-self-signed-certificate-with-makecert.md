---
author: Ivo Beerens
categories:
- certificate
- horizon
- view
date: "2014-06-24T09:03:38Z"
guid: http://www.ivobeerens.nl/?p=2856
id: 2856
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- certificate
- view
- VMware
title: Create a VMware Horizon View self signed certificate with makecert
url: /2014/06/24/create-a-vmware-horizon-view-self-signed-certificate-with-makecert/
---

With the command line Windows utility “makecert.exe” it is possible to create quickly a self-signed (private) certificate that can be used with VMware Horizon View. Makecert is part of the Windows Software Deployment Kit (SDK)for Windows 7 and 8. Below are the steps outlined to create a self-signed certificate using makecert.

- The SDK can be downloaded here, [link](http://www.microsoft.com/en-us/download/details.aspx?id=8279). Install the SDK and choose as feature to install “Windows Software Deployment”.
- After the installation copy the makecert.\* utility to the VMware View Connection server
- Open a elevated command prompt
- Create the self-signed root certificate, command: <span style="font-family: 'Courier New';">makecert -pe -n “CN=ViewRootCA” -ss root -sr LocalMachine -sky signature -r “ViewRootCA.cer”</span>

[![image](http://localhost/wp-content/uploads/2014/06/image_thumb6.png "image")](http://localhost/wp-content/uploads/2014/06/image7.png)

- Open certlm.msc and go to “Trusted Root Certification Authorities” and verify if the root certificate generated with makecert.exe exist. The root certificate can copied to all the servers and View Clients. If the clients are domain joined a Group Policy can be used to distribute the root certificate. More information can be found here, [link](http://technet.microsoft.com/en-us/library/cc772491.aspx).

[![image](http://localhost/wp-content/uploads/2014/06/image4_thumb1.png "image")](http://localhost/wp-content/uploads/2014/06/image41.png)

- Create a new self-signed certificate, command: <span style="font-family: 'Courier New';">makecert -pe -n “CN=viewcon02.beerens.local,cn=viewcon02” -ss my -sr LocalMachine -sky exchange -in “ViewRootCA” -is root -ir LocalMachine -sp “Microsoft RSA SChannel Cryptographic Provider” -sy 12 viewcon02.cer</span>

[![image](http://localhost/wp-content/uploads/2014/06/image_thumb7.png "image")](http://localhost/wp-content/uploads/2014/06/image8.png)

- The certificate is added to the personal store of the local computer

[![image](http://localhost/wp-content/uploads/2014/06/image19_thumb.png "image")](http://localhost/wp-content/uploads/2014/06/image19.png)

- Change the Friendly name of the newly created self-signed certificate to: vdm
- Remove the already existing self-signed certificate

[![image](http://localhost/wp-content/uploads/2014/06/image16_thumb.png "image")](http://localhost/wp-content/uploads/2014/06/image16.png)

- Restart the VMware View Connection Server service
- In the System Health dashboard the Connection Server system health gets green

[![image](http://localhost/wp-content/uploads/2014/06/image23_thumb.png "image")](http://localhost/wp-content/uploads/2014/06/image23.png)
