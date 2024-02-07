---
author: Ivo Beerens
categories:
- ESXi
- syslog
date: "2012-05-29T10:40:33Z"
guid: http://www.ivobeerens.nl/?p=1567
id: 1567
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- esxi
- syslog
title: vSphere Syslog Collector troubleshooting
url: /2012/05/29/vsphere-syslog-collector-troubleshooting/
---

During a VMware health check, I noticed that the syslog files aren’t updated anymore in the repository from he vSphere Syslog Collector server.

[![image](http://localhost/wp-content/uploads/2012/05/image_thumb13.png "image")](http://localhost/wp-content/uploads/2012/05/image14.png)

Here are some basic steps I used to troubleshoot this problem.

### **VMware ESXi hosts**

On the VMware ESXi hosts check the following settings:

– Syslog destination. Open the vSphere Client. On the ESXi server, open the **configuration** tab and select **advanced** Settings. Check the **Syslog.global.logHost** value. The format is: **protocol://FQDN:port** . For example **udp://syslog.beerens.local:514**

[![image](http://localhost/wp-content/uploads/2012/05/image_thumb14.png "image")](http://localhost/wp-content/uploads/2012/05/image15.png)

– Is the ESXi firewall port open for syslog traffic. Open the vSphere Client, on the ESXi server, open the Configuration tab, select Security Profile, Firewall and select Properties. Check if the syslog service is enabled.

[![image](http://localhost/wp-content/uploads/2012/05/image_thumb15.png "image")](http://localhost/wp-content/uploads/2012/05/image16.png)

### <font style="font-weight: bold">vSphere Syslog Collector</font>

On the vSphere Syslog Collector server check the following settings:

– Is the syslog port 514 (default) listening:

[![image](http://localhost/wp-content/uploads/2012/05/image_thumb16.png "image")](http://localhost/wp-content/uploads/2012/05/image17.png)

\- Reload and update the syslog configuration. On the ESXi host use the following command:

```
<pre lang="plain">esxcli system syslog reload
```

In PowerCLI, the following command can be used to reload the syslog settings:

```
<pre lang="plain">$esxCli = Get-EsxCli
$esxCli.system.syslog.reload()
```

– Is the Syslog Collector service started. Restart the Syslog Collector service if needed

[![image](http://localhost/wp-content/uploads/2012/05/image_thumb17.png "image")](http://localhost/wp-content/uploads/2012/05/image18.png)

After the reloading the syslog settings and restarting the **Syslog Collector service** the files begun to update again in the repository.
