---
title: "Quick Tip - PowerCLI Invalid server certificate"
date: "2018-07-18T11:45:19.000Z"
tags: 
  - "powercli"
  - "vmware"
---

When trying to connect with PowerCLI to a vCenter Server Appliance the following error occurred:

[![](images/powerclo-300x51.png)](https://www.ivobeerens.nl/wp-content/uploads/2018/07/powerclo.png)

> Connect-vIServer : 18-7-2018 13:20:10 Connect-VIServer Error: Invalid server certificate. Use Set-PowerCLIConfiguration to set the value for the InvalidCertificateAction option to Prompt if you'd like to connect once or to add a permanent exception for this server.

As stated in the error, the Set-PowerCLIConfiguration command can be used to ignore the certificate check using the following syntax:

\[code language="powershell"\] Set-PowerCLIConfiguration -InvalidCertificateAction Ignore -Confirm:$false \[/code\]

After this command you're able to connect to the vCenter without the certificate error.

[![](images/2-300x100.png)](https://www.ivobeerens.nl/wp-content/uploads/2018/07/2.png)
