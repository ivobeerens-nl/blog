---
author: Ivo Beerens
categories:
- horizon
- view
- VMware
date: "2014-04-09T15:33:08Z"
guid: http://www.ivobeerens.nl/?p=2730
id: 2730
ssb_fbshare_counts:
- "4"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:4;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "4"
tags:
- horizon
- view
- VMware
title: What&rsquo;s new in VMware Horizon 6
url: /2014/04/09/vmware-horizon-6-whats-new/
---

VMware Horizon 6 has been today announced. VMware Horizon 6 has five major enhancements:

- Cloud Pod Architecture.
- Remote Desktop Session Host (RDS) Hosted Apps
- Virtual SAN
- Application Catalog
- vCops for View 6

Here is an overview picture of the Horizon 6 architecture:

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb.png "image")](http://localhost/wp-content/uploads/2014/04/image.png)

#### Cloud Pod Architecture

In version 5 Horizon View supports 10.000 desktops in a Pod. If you need to to have more or than 10.000 desktops or needed to span a datacenter another Pod was needed. With the Cloud Pod Architecture the following improvements has been made :

- Enable Horizon deployments across multiple datacenters
- New data layer replication across all Horizon Connection Servers (such as pool configurations and user entitlements).
- Support single namespace for end users with a global URL
- Global entitlement layer to assign and manage desktops and users

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb1.png "image")](http://localhost/wp-content/uploads/2014/04/image1.png)

Benefits:

- Scale Horizon View deployments to multiple datacenter above 10.000 desktops
- Support Active/Active and DR use case of Horizon deployments
- Support geo-reaming users

Maximums of the Cloud Pod Architecture

| **Description** | **Number** |
|---|---|
| Number of sites (datacenters) | 2 |
| Number of Pods | 4 |
| Number of users/desktops (sessions) | 20.000 |

The Horizon 6 View infrastructure servers supports Windows Server 2012 R2 as Operating System.

#### RDS Hosted Apps

Prior Horizon 6 VMware only offers a VDI desktops. With RDS Hosted Apps in Horizon 6, VMware offers access to applications and full desktops running on Microsoft Remote Desktop Services Hosts with the PCoIP and Blast protocol. The RDS apps are available to the Horizon View broker.

Benefits

- Windows 2008 and 2012 Microsoft Remote Desktop Services Hosts are supported
- Seamless local look, feel and interaction for users
- Works with Windows and Non-Windows devices such as Windows XP, Windows 7 and Windows 8 desktops, laptops and thin clients, iOS and Android tablets and Mac OSX. A client for Linux will be available soon

In the View clients the full desktops and RDSH applications looks as follows:

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb2.png "image")](http://localhost/wp-content/uploads/2014/04/image2.png)

#### Virtual SAN for Horizon View Desktops

In Horizon View 5.3.1 support for VSAN was added. It was available as separate product. Now in Horizon 6 VSAN is added for free in the Horizon 6 Advanced and Enterprise Edition!

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb3.png "image")](http://localhost/wp-content/uploads/2014/04/image3.png)

#### Application Catalog

The Application Catalog offers a unified workspace for applications. One portal to for all applications (Local ThinApps, Citrix XenApp, SAAS and Remote Apps) from different devices.

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb4.png "image")](http://localhost/wp-content/uploads/2014/04/image4.png)

The Application Catalog key themes are:

- XenApp integration in the Application catalog
- ThinApp package delivery on any Windows desktop
- Office 365 and non-SAML web apps
- Improved resource management &amp; categorization
- Seamless integration with Horizon View

The application catalog has multi-forest Active Directory support and can be easily customized by changing logos, login prompt, application launchers, backgrounds etc.

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb5.png "image")](http://localhost/wp-content/uploads/2014/04/image5.png)

#### vCops for View 6

vCenter Operations Manager for View 6 has the following new improvements:

- Horizon 6 support
- 25K concurrent users per instance
- Single integrated console for all vCOPs support environments (desktop, server etc)
- Application &amp; In Guest Metrics. Drill down to the process level for key resource consumption per user and application

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb6.png "image")](http://localhost/wp-content/uploads/2014/04/image6.png)

#### Licenses

Horizon 6 has three new editions available:

- **Horizon View Standard Edition**: Delivers simple, high-performance VDI-based virtual desktops with a great user experience

- **Horizon Advanced Edition**: Offers the lowest cost solution for virtual desktop and application management, optimized storage with VMware Virtual SAN, image management and a unified workspace that supports hosted desktops and applications.

- **Horizon Enterprise Edition**: Delivers a cloud-ready solution for virtual desktops and applications with advanced cloud automation and management capabilities for hybrid cloud flexibility.

More information can be found on the pricing page, [link](http://www.vmware.com/nl/products/horizon-view/pricing.html) .

The Horizon 6 enhancements are a big step for the End-User Computing (EUC) market!

More information:

- VMware Horizon 6 Technical Overview link
- Horizon View 6.0 Integration with VMware Virtual SAN link
- VMware Horizon FAQ [link](https://www.vmware.com/files/pdf/products/horizon/VMware-Horizon-FAQ.pdf)
