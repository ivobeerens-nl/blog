---
title: "Unable to join domain when deploy a template using guest customization specification"
date: "2012-03-22T10:26:44.000Z"
categories: 
  - "template"
  - "vcenter-2"
  - "vsphere"
tags: 
  - "template"
  - "vcenter"
  - "vpshere"
---

At a customer I was unable to join a domain when deploying a template from vCenter using a guest customization specification. This only happened with Windows 2008 R2 and Windows 7 templates.

To solve this problem, you need the do the following in the guest customization specification:

\- Enter the FQDN name in Windows Server Domain field (1)

\- Enter the [user@domain\_FQDN](mailto:user@domain_FQDN) in the username field (2)

[![image](images/image_thumb23.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/03/image23.png)

I used the NetBIOS domain name in the “Windows Server Domain” field and “domain\\username” in the username field what doesn’t work with Windows 2008 R2 and Windows 7 anymore.

More information can be found [**here**](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1012314) state that you need to fill in:

\[ad#banner\]
