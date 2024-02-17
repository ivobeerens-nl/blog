---
author: Ivo Beerens
categories:
- horizon
- view
- VMware
date: "2014-03-20T21:15:02Z"
guid: http://www.ivobeerens.nl/?p=2709
id: 2709
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Horizon View
- view
- VMware
title: Install a wildcard certificate on a VMware Horizon View Security Server
url: /2014/03/20/install-a-wildcard-certificate-on-a-vmware-horizon-view-security-server/
---

On a View Security Server I needed to change the default self signed certificate to a signed wildcard certificate. The customer had a wildcard certificate that didn’t include the private key. A certificate that include the private key is a requirement for a VMware View Security server.

If you have the certificate (\*.cer or \*.crt) and private key (\*.key), convert it to a PCKS#12 (PFX) format before you import the certificate. To create a certificate that include the private key I used the following steps:

- Download and install OpenSSL and Visual C++ 2008 Redistributables. [Link](http://slproweb.com/products/Win32OpenSSL.html)
- The install directory of OpenSSL is: *C:\\OpenSSL-Win64\\*
- <span style="font-size: small;">Place the certificate (\*.cer or \*.crt) and private key (\*.key) file in the *C:\\OpenSSL-Win64\\bin directory* directory </span>
- Open a command prompt and set the environment variable: *Set OPENSSL\_CONF=c:\\OpenSLL-Win64\\bin\\openssl.cfg*
- Create another environment variable: Set RANDFILE = .rnd
- Generate a PCKS#12 (PFX) keystore file from the private key and certificate file. Syntax example: *OpenSSL.exe pkcs12 –export -out newcertificatename.pfx –inkey privatekey.key –in certificate.crt*

[![image](http://localhost/wp-content/uploads/2014/03/image_thumb3.png "image")](http://localhost/wp-content/uploads/2014/03/image3.png)

- Enter the password for the certificate

The next step is to Import the certificate on the security server:

- Open the MMC on the Security Server and add the Certifcates snap-in
- In the Windows local computer store import the generated P12 certificate
- Type the password for the private key
- Make sure the certificate is exportable
- Change the friendly name to “*vdm*” and make sure that the friendly name of the self signed certificate is changed to something else
- Restart the View Connection Security service

[![image](http://localhost/wp-content/uploads/2014/03/image_thumb4.png "image")](http://localhost/wp-content/uploads/2014/03/image4.png)

The new wildcard certificate has a private key and is trusted in the VMware View client and on the View Administrator page.

| [![image](http://localhost/wp-content/uploads/2014/03/image_thumb5.png "image")](http://localhost/wp-content/uploads/2014/03/image5.png) | [![image](http://localhost/wp-content/uploads/2014/03/image_thumb6.png "image")](http://localhost/wp-content/uploads/2014/03/image6.png) |
|---|---|

More information about certificates can be found in the Obtaining SSL Certificates for VMware Horizon View Servers. [Link](http://pubs.vmware.com/view-52/topic/com.vmware.ICbase/PDF/horizon-view-52-obtaining-certificates.pdf)
