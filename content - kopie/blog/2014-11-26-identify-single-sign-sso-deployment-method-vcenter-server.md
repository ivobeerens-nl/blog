---
author: Ivo Beerens
categories:
- sso
- VMware
- vSphere
date: "2014-11-26T15:20:12Z"
guid: http://www.ivobeerens.nl/?p=3218
id: 3218
ssb_fbshare_counts:
- "5"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:5;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "5"
tags:
- Deployment
- SRM
- sso
- VMware
- vSphere
title: Identify the Single Sign-On (SSO) deployment method for the vCenter Server
url: /2014/11/26/identify-single-sign-sso-deployment-method-vcenter-server/
---

With vSphere 5.5 you have the following deployment methods for Single Sign-On (SSO):

- vCenter Single Sign-On for your first vCenter Server
- vCenter Single Sign-On for an additional vCenter Server in an existing site (formerly HA Cluster)
- vCenter Single Sign-On for an additional vCenter Server with a new site (formerly Multisite)

Once SSO is installed it can be usefull to identify what deployment options are used for example in a Site Recovery Manager (SRM) deployment. The following steps can be used to identify what deployment option are used for SSO on a vCenter Server 5.5:

- Browse to the following directory on the vCenter Server: **C:\\ProgramData\\VMware\\VMware VirtualCenter**
- Use a type command to display the “**LS\_ServiceID.prop**” file. The file contains the site name and indentifier. For example: **SiteName1**:10b042be-9b7a-467c-aa05-047a895c60fb
- Repeat the above steps on the other vCenter Server(s)

If the string is the same in both sites SSO has deployed as: “vCenter Single Sign-On for an additional vCenter Server in an existing site”. If the string is different, the vCenter Single Sign-On instance is deployed as: “vCenter Single Sign-On for an additional vCenter Server with a new site”.
