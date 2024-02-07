---
author: Ivo Beerens
categories:
- template
- vcenter
- vSphere
date: "2012-03-22T11:26:44Z"
guid: http://www.ivobeerens.nl/?p=1435
id: 1435
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- template
- vCenter
- vpshere
title: Unable to join domain when deploy a template using guest customization specification
url: /2012/03/22/unable-to-join-domain-when-deploy-a-template-using-guest-customization-specification/
---

<font color="#000000">At a customer I was unable to join a domain when deploying a template from vCenter using a guest customization specification. This only happened with Windows 2008 R2 and Windows 7 templates. </font>

<font color="#000000">To solve this problem, you need the do the following in the guest customization specification:</font>

<font color="#000000">– Enter the FQDN name in Windows Server Domain field (1)</font>

<font color="#000000">– Enter the </font>[<font color="#000000">user@domain\_FQDN</font>](mailto:user@domain_FQDN)<font color="#000000"> in the username field (2)</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2012/03/image_thumb23.png "image")</font>](http://localhost/wp-content/uploads/2012/03/image23.png)

<font color="#000000">I used the NetBIOS domain name in the “Windows Server Domain” field and “domain\\username” in the username field what doesn’t work with Windows 2008 R2 and Windows 7 anymore.</font>

<font color="#000000">More information can be found </font>[<font color="#000000">**here**</font>](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1012314)<font color="#000000"> state that you need to fill in: </font>

<font color="#000000"> </font>

\[ad#banner\]

<font color="#000000"> </font>
