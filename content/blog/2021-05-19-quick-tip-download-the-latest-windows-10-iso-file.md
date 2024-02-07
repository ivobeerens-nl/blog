---
author: Ivo Beerens
categories:
- Windows 10
- Windows 11
date: "2021-05-19T20:55:54Z"
guid: https://www.ivobeerens.nl/?p=7940
id: 7940
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- windows 10
- Windows 11
title: 'Quick Tip: Download the latest Windows 11 ISO files'
url: /2021/05/19/quick-tip-download-the-latest-windows-10-iso-file/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

In my lab environment, I use the latest Windows 10 or Windows 11 versions (for example the new Windows 11 23H2) for creating and testing golden images for VDI environments.

To download the latest Windows ISOs file I use the Windows Media Creation Tool. This is a Windows-based tool. When starting the Windows Media Creation Tool it opens a Graphical User Interface and you are able to download Windows Home (N), Education (N), and the Pro (N) ISO. To download the Enterprise version you need to enter the command line. Here are the steps explained to download a Windows 10/11 Enterprise ISO:

- Download the Windows 10 Media Creation Tool ([Link)](https://www.microsoft.com/en-us/software-download/windows10) or Windows 11 Media Creation Tool ([Link](https://www.microsoft.com/software-download/windows11))
- Select: “Download Tool now”
- Open the command line
- Use the following command to download the English 64-bits Windows 10/11 Enterprise ISO:

```powershellmediacreationtool.exe /Eula Accept /Retail /MediaArch x64 /MediaLangCode en-US /MediaEdition Enterprise```

- To download the Dutch 64-bits Windows 10/11 Enterprise ISO use the following command:

```powershellMediaCreationTool.exe /Eula Accept /Retail /MediaArch x64 /MediaLangCode nl-NL /MediaEdition Enterprise```

- Enter the product key “NPPR9-FWDCX-D2C8J-H872K-2YT43”. The KMS client keys can be found here: [link](https://docs.microsoft.com/sl-si/windows-server/get-started/kmsclientkeys)

[![](http://localhost/wp-content/uploads/2021/05/1-300x266.jpg)](http://localhost/wp-content/uploads/2021/05/1.jpg)

- Select: Create installation media (USB flash drive, DVD, or ISO file) for another PC

[![](http://localhost/wp-content/uploads/2021/05/2-300x265.jpg)](http://localhost/wp-content/uploads/2021/05/2.jpg)

- Select “Iso file” and browse to a location to store the ISO. You need at least 8GB free on the C-drive and the ISO size is between 4 and 5 GB.

[![](http://localhost/wp-content/uploads/2021/05/3-300x265.jpg)](http://localhost/wp-content/uploads/2021/05/3.jpg)

- The download of the Windows 10 ISO starts.

[![](http://localhost/wp-content/uploads/2021/05/4-300x264.jpg)](http://localhost/wp-content/uploads/2021/05/4.jpg)

Once the downloading of the ISO is completed it’s ready for use.

[![](http://localhost/wp-content/uploads/2021/05/w10-21h1-01-300x235.jpg)](http://localhost/wp-content/uploads/2021/05/w10-21h1-01.jpg)
