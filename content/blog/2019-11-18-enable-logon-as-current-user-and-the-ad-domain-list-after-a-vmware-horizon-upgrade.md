---
author: Ivo Beerens
categories:
- Uncategorized
date: "2019-11-18T20:18:48Z"
guid: https://www.ivobeerens.nl/?p=7168
id: 7168
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- VMware Horizon
title: '&#8220;Logon As Current User&#8221; and the &#8220;AD domain list&#8221; options
  default disabled after a VMware Horizon upgrade'
url: /2019/11/18/enable-logon-as-current-user-and-the-ad-domain-list-after-a-vmware-horizon-upgrade/
---

When upgrading a VMware Horizon Connection server to version 7.8 or higher the following message appears during the upgrade.

[![](http://localhost/wp-content/uploads/2019/11/1-300x141.jpg)](http://localhost/wp-content/uploads/2019/11/1.jpg)

This means the following settings are disabled after the upgrade:

- Login As Current User will no longer work when selecting the “Log in as current user” in the Horizon Client
- List of user domains will be withheld from Horizon clients

| [![](http://localhost/wp-content/uploads/2019/11/domainon-300x168.jpg)](http://localhost/wp-content/uploads/2019/11/domainon.jpg) | [![](http://localhost/wp-content/uploads/2019/11/client-300x198.jpg)](http://localhost/wp-content/uploads/2019/11/client.jpg) |
|---|---|

With this option, the Active Directory domain name is not visible and replace \*DefaultDomain\*

These settings are disabled to improve security but sometimes after a Horizon environment upgrade one or more settings needs re-enabled again. Here are the steps to enable these settings:

## **Enabling Login As Current User**

Allow the Connection Server to accept logon as current user authentication

1. Open: ***https://fqdn/admin***
2. Enter the user name and password
3. Click on “View Configuration” and select Servers
4. Select the Connection Servers tab
5. Select the Connection Server and click on Edit
6. Select the Authentication tab
7. Scroll down the bottom and select “Accept logon as current user”
8. Click on OK

Repeat steps 5-8 for each VMware Horizon Connection Server.

[![](http://localhost/wp-content/uploads/2019/11/3-300x135.jpg)](http://localhost/wp-content/uploads/2019/11/3.jpg)

## **Enabling the domain list in the Horizon Client**

1. Open: https://fqdn/admin
2. Enter the user name and password
3. Click on “View Configuration” and Edit the “Global Settings”
4. Scroll down and select “Send domain list”
5. Click on OK

[![](http://localhost/wp-content/uploads/2019/11/2-300x136.jpg)](http://localhost/wp-content/uploads/2019/11/2.jpg)

After enabling this global setting the Active Directory domain is visible again and it is possible to select another AD domain.

[![](http://localhost/wp-content/uploads/2019/11/domainon-300x168.jpg)](http://localhost/wp-content/uploads/2019/11/domainon.jpg)
