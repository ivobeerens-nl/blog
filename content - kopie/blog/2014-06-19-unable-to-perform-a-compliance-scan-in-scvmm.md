---
author: Ivo Beerens
categories:
- Hyper-V
- scvmm
date: "2014-06-19T08:23:50Z"
guid: http://www.ivobeerens.nl/?p=2832
id: 2832
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- hyper-v
- scvmm
title: Unable to perform a Compliance Scan in SCVMM
url: /2014/06/19/unable-to-perform-a-compliance-scan-in-scvmm/
---

In System Center Virtual Machine Manager (SCVMM) an Update (WSUS) Server is added, so VMM can be used to update the hosts with Windows patches.When trying to scan a cluster of hosts for compliance the following error occurred:

**Error (24035)**

Compliance scan failed with error: 80244017.

**Recommended Action:**

Ensure the WINHTTP proxy settings are correctly configured for the communications with WSUS. If WSUS is configured to use SSL ensure the WSUS certificate is installed in the trusted Root CA for the machine and then try the operation again.

[![image](http://localhost/wp-content/uploads/2014/06/image_thumb3.png "image")](http://localhost/wp-content/uploads/2014/06/image3.png)

The cluster consist of several Microsoft Hyper-V Server 2012 R2 hosts. All the hosts are configured with a proxy server during the initial installation. After resetting the proxy server per host, the SCVMM was able to perform a compliance scan without errors. The following command is used to reset the proxy server configuration on the core version:

<font face="Courier New">netsh winhttp reset proxy</font>

[![image](http://localhost/wp-content/uploads/2014/06/image4_thumb.png "image")](http://localhost/wp-content/uploads/2014/06/image4.png)
