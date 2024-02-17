---
author: Ivo Beerens
categories:
- horizon
- view
date: "2013-03-20T15:06:49Z"
guid: http://www.ivobeerens.nl/?p=2242
id: 2242
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:2;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
tags:
- blast
- horizon
- security server
- unity
- view
- VMware
title: VMware Horizon View and HTML access (Blast protocol)
url: /2013/03/20/vmware-horizon-view-and-html-access-blast-protocol/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

With the release of the **VMware Horizon View Feature Pack 1** for VMware Horizon View 5.2 it possible to connect with HTML5 to your View desktop. This without installing additional software. The new HTML5 protocol is called Blast. Connecting by using the Blast HTML protocol can be handy when you are on a device that does not have the VMware View client installed.

The VMware Horizon View Feature Pack 1 contains the following two main components:

- **Remote Experience Agent installer**
- **HTML Access installer**

**Remote Experience Agent installer** contains:

- HTML Access Agent: The HTML Access Agent allows users to connect to Horizon View desktops by using HTML Access
- Unity Touch: With Unity Touch, tablet and smart phone users can easily browse, search, and open Windows applications and files, choose favorite applications and files,and switch between running applications, all without using the Start menu or Taskbar. Unity touch requires a VMware View Client

This component is installed on the View Desktop (XP SP3, Windows Vista (32-bit), Windows 7 or 8 )

**HTML Access installer**: This installer configures View Connection Server instances to allow users to select HTML Access to connect to desktops. After you run the HTML Access installer, the View Portal displays an HTML Access icon in addition to the View Client icon.

This component is installed on the Blast Secure Gateway know as View Connection Server (Not the Security Server).

Here is an overview of the components and firewall ports that’s needs to be opened:

[![VMware Blast](http://localhost/wp-content/uploads/2013/03/VMware-Blast_thumb1.jpg "VMware Blast")](http://localhost/wp-content/uploads/2013/03/VMware-Blast1.jpg)

A single security server can support up to 100 simultaneous connections to Web clients using the Blast protocol. For a complete list and drawing of the firewall ports that needs to be opened in a VMware View Security Server environment see my earlier post [here](http://localhost/2013/03/05/tips-for-implementing-a-vmware-horizon-view-security-server/).

In the View Administrator the connections using a the Blast protocol can be monitored:

[![image](http://localhost/wp-content/uploads/2013/03/image_thumb4.png "image")](http://localhost/wp-content/uploads/2013/03/image4.png)

Unity Touch is supported on the following Horizon View Client versions:

- Horizon View Client for iOS 2.0 or later
- Horizon View Client for Android 2.0 or later

Unity Touch is supported on the following mobile device operating systems:

- iOS 5.0 and later
- Android 3 (Honeycomb)

The following Web browsers are supported:

- Chrome 22 or later
- Internet Explorer 9 or later
- Safari 5.1.7 or later
- Firefox 16 or later
- Mobile Safari on iOS devices running iOS 6 or later

Don’t expect: that the Blast protocol offers:

- The same performance as PCoIP!
- USB and multimedia redirection
- ThinPrint support

But the Blast HTML protocol can be handy when you are on a device that does not have the VMware View client installed.

| [![image](http://localhost/wp-content/uploads/2013/03/image_thumb5.png "image")](http://localhost/wp-content/uploads/2013/03/image5.png) | [![image](http://localhost/wp-content/uploads/2013/03/image_thumb6.png "image")](http://localhost/wp-content/uploads/2013/03/image6.png) |
|---|---|
| View Portal. Choose between the View Client or HTML access | Logon screen HTML access |
| [![foto (1)](http://localhost/wp-content/uploads/2013/03/foto-1_thumb.png "foto (1)")](http://localhost/wp-content/uploads/2013/03/foto-1.png) | [![foto](http://localhost/wp-content/uploads/2013/03/foto_thumb.png "foto")](http://localhost/wp-content/uploads/2013/03/foto.png) |
| Unity touch from iPhone | Unity touch from iPhone |
