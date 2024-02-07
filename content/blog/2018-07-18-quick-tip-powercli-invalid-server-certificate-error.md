---
author: Ivo Beerens
categories:
- Uncategorized
date: "2018-07-18T13:45:19Z"
guid: https://www.ivobeerens.nl/?p=5728
id: 5728
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- PowerCLI
- VMware
title: Quick Tip - PowerCLI Invalid server certificate
url: /2018/07/18/quick-tip-powercli-invalid-server-certificate-error/
---

When trying to connect with PowerCLI to a vCenter Server Appliance the following error occurred:

[![](http://localhost/wp-content/uploads/2018/07/powerclo-300x51.png)](http://localhost/wp-content/uploads/2018/07/powerclo.png)

> Connect-vIServer : 18-7-2018 13:20:10 Connect-VIServer Error: Invalid server certificate. Use Set-PowerCLIConfiguration to set the value for the InvalidCertificateAction option to Prompt if you’d like to connect once or to add a permanent exception for this server.

As stated in the error, the Set-PowerCLIConfiguration command can be used to ignore the certificate check using the following syntax:

```powershell  
Set-PowerCLIConfiguration -InvalidCertificateAction Ignore -Confirm:$false  
```

After this command you’re able to connect to the vCenter without the certificate error.

[![](http://localhost/wp-content/uploads/2018/07/2-300x100.png)](http://localhost/wp-content/uploads/2018/07/2.png)
