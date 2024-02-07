---
author: Ivo Beerens
categories:
- Hyper-V
- Powershell
- windows 8
date: "2012-03-07T15:13:45Z"
guid: http://www.ivobeerens.nl/?p=1372
id: 1372
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hyper-v
- Powershell
- windows 8
title: Windows Server 2012 PowerShell Cmdlets for Hyper-V help
url: /2012/03/07/windows-server-8-powershell-cmdlets-for-hyper-v-help/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

<span style="color: #000000;">In Windows 2008 &amp; Windows2008 R2 there were no official PowerShell Cmdlets available for Hyper-V. This is changed in Windows 2012 and Windows 8. Windows Server 2012 and 8 has 162 or more PowerShell Cmdlets available for Hyper-V. Windows 8 uses PowerShell version 3.</span>

<span style="color: #000000;">Cmdlets are very powerful, that lets you automate all aspects of Hyper-V. Here some guidance how-to find the Cmdlets you need.</span>

<span style="color: #000000;">To view all the Hyper-V PowerShell Cmdlets:</span>

```
<pre lang="plain">Get-Command -Module Hyper-V
```

<span style="color: #000000;">To search for Cmdlets, for example with the name “host” in it: </span>

```
<pre lang="plain">Get-Command -Module Hyper-V -Noun *host*
```

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/03/image_thumb.png "image")</span>](http://localhost/wp-content/uploads/2012/03/image.png)

<span style="color: #000000;">To get the Cmdlet syntax:</span>

```
<pre lang="plain">Get-VMHost -?
```

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/03/image_thumb1.png "image")</span>](http://localhost/wp-content/uploads/2012/03/image1.png)

<span style="color: #000000;">Get the Cmdlet syntax and available parameters, details and examples:</span>

```
<pre lang="plain">get-Help Get-VMHost -Full
```

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/03/image_thumb2.png "image")</span>](http://localhost/wp-content/uploads/2012/03/image2.png)

<span style="color: #000000;">More information over the Hyper-V Cmdlets can be found [here](http://technet.microsoft.com/en-us/library/hh848559.aspx). PowerShell 3.0 is available as Community Technology Preview (CTP) found here.</span>

<span style="color: #000000;"> </span>

<span style="color: #000000;">\[ad#banner\]</span>
