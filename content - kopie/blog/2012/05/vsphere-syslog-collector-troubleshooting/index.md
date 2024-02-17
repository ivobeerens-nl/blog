---
title: "vSphere Syslog Collector troubleshooting"
date: "2012-05-29T08:40:33.000Z"
categories: 
  - "esxi"
  - "syslog"
tags: 
  - "esxi-2"
  - "syslog"
---

During a VMware health check, I noticed that the syslog files aren’t updated anymore in the repository from he vSphere Syslog Collector server.

[![image](images/image_thumb13.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/05/image14.png)

Here are some basic steps I used to troubleshoot this problem.

### **VMware ESXi hosts**

On the VMware ESXi hosts check the following settings:

\- Syslog destination. Open the vSphere Client. On the ESXi server, open the **configuration** tab and select **advanced** Settings. Check the **Syslog.global.logHost** value. The format is: **protocol://FQDN:port** . For example **udp://syslog.beerens.local:514**

[![image](images/image_thumb14.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/05/image15.png)

\- Is the ESXi firewall port open for syslog traffic. Open the vSphere Client, on the ESXi server, open the Configuration tab, select Security Profile, Firewall and select Properties. Check if the syslog service is enabled.

[![image](images/image_thumb15.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/05/image16.png)

### vSphere Syslog Collector

On the vSphere Syslog Collector server check the following settings:

\- Is the syslog port 514 (default) listening:

[![image](images/image_thumb16.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/05/image17.png)

\-  Reload and update the syslog configuration.  On the ESXi host use the following command:

esxcli system syslog reload

In PowerCLI, the following command can be used to reload the syslog settings:

$esxCli = Get-EsxCli
$esxCli.system.syslog.reload()

\- Is the Syslog Collector service started. Restart the Syslog Collector service if needed

[![image](images/image_thumb17.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/05/image18.png)

After the reloading the syslog settings and restarting the **Syslog Collector service** the files begun to update again in the repository.
