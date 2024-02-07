---
author: Ivo Beerens
categories:
- lync
- view
- VMware
date: "2013-04-03T14:10:29Z"
guid: http://www.ivobeerens.nl/?p=2255
id: 2255
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- lync
- view
- VMware
title: VMware Horizon View and Microsoft Lync 2013 support
url: /2013/04/03/vmware-horizon-view-and-microsoft-lync-2013-support/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

VMware Horizon View 5.2 adds support for Microsoft Lync 2013 with audio en video. With Microsoft Lync 2010, only VoIP was supported, but required a dedicated IP-based phone. Microsoft and VMware collaborated to bring Lync 2013 support to the View 5.2 desktop.

Here is a list of supported features with Lync 2013 in VMware View:

| **Features** | **Support/Unsupported** |
|---|---|
| **Presence** | Supported |
| **Instant Message** | Supported |
| **Desktop Sharing** | Supported |
| **Application Sharing** | Supported |
| **PowerPoint Sharing** | Supported |
| **Whiteboards** | Supported |
| **File transfer** | Supported |
| **Online meetings** | Supported |
| **Office Integration** | Supported |
| **Audio** | Supported (with Lync 2010, this used to only be supported via IP-Phone) |
| **Video** | Supported (with Lync 2010, this was never supported) |
| **Recording audio** | Unsupported |

All the media processing is offloaded from the datacenter to the client endpoint. The following diagram highlights the different components and the communication flow of the VMware View and Microsoft Lync 2013:

[![image](http://localhost/wp-content/uploads/2013/04/image_thumb.png "image")](http://localhost/wp-content/uploads/2013/04/image.png)

The VDI Plug-in is a standalone application that needs the be installed on the local Windows computer and allows the use of local audio and video devices with the Lync 2013 client running in the View Desktop. Audio and Video traffic is sent point-to-point between the endpoints.

On the moment only Windows 7 SP1 is supported as client OS and View desktop.

VMware has released a guide about the installation and configuration of Lync 2013 with VMware View 5.2. The document can be found [here](http://communities.vmware.com/servlet/JiveServlet/downloadBody/22775-102-1-30309/VMwareViewandMicrosoftLync2013InstallationGuidev1.0.doc)
