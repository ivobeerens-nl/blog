---
author: Ivo Beerens
categories:
- Horizon View
- VMware View
date: "2015-06-05T11:42:21Z"
guid: http://www.ivobeerens.nl/?p=3871
id: 3871
ssb_fbshare_counts:
- "6"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:6;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "6"
tags:
- view
- VMware Horizon
title: VMware Horizon View Client Drive Redirection
url: /2015/06/05/vmware-horizon-view-client-drive-redirection/
---

On of the new features of VMware Horizon 6 version 6.1.1 is Client Drive Redirection (CDR). Microsoft RDS and Citrix already have CDR for many years in there product. Now this handy feature is available in Horizon View. CDR is supported on VDI desktops (single-user) and RDS desktops and applications on Windows and as Tech Preview on Mac OS X clients.

Here’s a quick overview how-to enable Client Drive Redirection (CDR):

**Requirements**

- Horizon View 6.1.1 environment (Connection Server, composer etc.)
- View Agent 6.1.1 or later
- VMware Horizon Client 3.4.0 build-2769709

Install the Horizon View Agent. During the installation of the VMware Horizon Agent enable the Client Drive Redirection feature.

[![agent](http://localhost/wp-content/uploads/2015/06/agent-300x227.png)](http://localhost/wp-content/uploads/2015/06/agent.png)

After installing the new Horizon View Agent is deployed on the Horizon View environment, connect with new 3.4.0 Horizon Client. When connecting for the first time to the there’s a pop-up asking to access your local files. Make sure to allow this and select “Do not show this dialog again”.

[![View Deskstop](http://localhost/wp-content/uploads/2015/06/View-Deskstop-300x131.png)](http://localhost/wp-content/uploads/2015/06/View-Deskstop.png)

In the Horizon View Client there is a option called “Share Folders”. In the sharing box add local drives and folders to share in the VDI desktop session.

[![0_sharing](http://localhost/wp-content/uploads/2015/06/0_sharing.png)](http://localhost/wp-content/uploads/2015/06/0_sharing.png) [![Sharing](http://localhost/wp-content/uploads/2015/06/Sharing-300x233.png)](http://localhost/wp-content/uploads/2015/06/Sharing.png)

In the Windows Explorer the drives and folders that are mapped are visible.

[![files](http://localhost/wp-content/uploads/2015/06/files-300x181.png)](http://localhost/wp-content/uploads/2015/06/files.png)

**Note**: With Client Drive Redirection (CDR), the folders and files that are sent across the network are NOT encrypted!
