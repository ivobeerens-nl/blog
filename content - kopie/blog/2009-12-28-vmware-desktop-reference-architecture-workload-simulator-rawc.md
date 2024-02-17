---
author: Ivo Beerens
categories:
- VDI
- virtualization
- VMware
- VMware View
date: "2009-12-28T13:11:31Z"
guid: http://www.ivobeerens.nl/?p=447
id: 447
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- desktop
- VDI
- view
- View 4
- VMware
title: VMware Desktop Reference Architecture Workload Simulator (RAWC)
url: /2009/12/28/vmware-desktop-reference-architecture-workload-simulator-rawc/
---

VMware released last week the desktop Reference Architecture Workload Simulator (RAWC).

 <font face="Verdana"><font size="1"><font color="#000000"><span style="line-height: 115%; font-family: "Arial","sans-serif"; font-size: 10pt"> </span></font></font></font>

> <span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">When validating VMware View™ designs it is important to simulate real world usage as closely as possible. The </span>*<span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: 'Arial,Italic'">Desktop Reference Architecture Workload SImulator </span>*<span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">(RAWC) can be used to simulate a user workload in a typical </span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Microsoft Windows® desktop environment. </span>
> 
> <span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Desktop RAWC runs on a Windows XP guest operating system and is executed on each desktop virtual machine </span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">(VM) on one or more ESX™ hosts. Each target desktop VM is equipped to run a RAWC workload that simulates </span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">typical user behavior, running an application set commonly used across a broad array of desktop environments. </span>
> 
> <span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial"></span>
> 
> <span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">[![image](http://localhost/wp-content/uploads/2009/12/image_thumb.png "image")](http://localhost/wp-content/uploads/2009/12/image.png) </span>
> 
> <span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial"></span>
> 
> <span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">The workload has a set of randomly executed functions that perform operations on a variety of applications. </span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Each test is configured using the Desktop RAWC UI </span>
> 
> <span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial"> [![image](http://localhost/wp-content/uploads/2009/12/image_thumb1.png "image")](http://localhost/wp-content/uploads/2009/12/image1.png) </span>
> 
> <span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial"></span>
> 
> <span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">The UI enables you to save and retrieve test parameters, </span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">create log folders, and define unique workloads based on Active Directory groups. You can use the UI to increase </span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">the load or adjust the user behavior, such as the number of words per minute that are typed and the delay between </span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">applications being launched. </span>
> 
> <span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">The workload configuration typically used includes Microsoft Word, Excel, PowerPoint, Outlook, Internet Explorer, </span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Windows Media Player, Java, Adobe Acrobat, McAfee Virus Scan, and 7-Zip. During the execution of the workload, </span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">multiple applications are opened at the same time and windows are minimized and maximized as the workload </span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">progresses, randomly switching between each application. Individual application operations that are randomly </span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">performed can include: </span>
> 
> <span style="font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Microsoft Word – Open, minimize, maximize, close, insert text, save modifications </span>
> 
> <span style="font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Microsoft Word (Random) – Open, minimize, maximize, close, write random words/numbers, save modifications </span>
> 
> <span style="font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Microsoft Excel – Open, minimize, maximize, close, write random numbers, insert/delete columns/rows, copy/paste formulas, save modifications </span>
> 
> <span style="font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Microsoft PowerPoint – Open, minimize, maximize, close, conduct a slide show presentation </span>
> 
> <span style="font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Microsoft Out</span>**<span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: 'Arial,Bold'">l</span>**<span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">ook – Open, minimize, maximize, close, create/send emails </span>
> 
> <span style="font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Internet Explorer – Open, minimize, maximize, close, browse page </span>
> 
> <span style="font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Windows Media Player – Open, close, view a video </span>
> 
> <span style="font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Java – Compile a java project comprised of several hundred files using the JDK to create a software </span>
> 
> <span style="font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">engineering type of workload </span>
> 
> <span style="font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">Adobe Acrobat Reader – Open, minimize, maximize, close, browse pages in PDF document </span>
> 
> <span style="font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">McAfee Anti-virus – Real time scanning </span>
> 
> <span style="line-height: 115%; font-family: symbol; font-size: 8pt; mso-fareast-font-family: symbol; mso-bidi-font-family: symbol"><span style="mso-list: ignore">·<span style="font: 7pt "Times New Roman""> </span></span></span><span style="line-height: 115%; font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">7-Zip – Open, close, compress a large file</span><span style="line-height: 115%; font-family: "Verdana","sans-serif"; font-size: 8pt"> </span>

<span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial"><font face="Arial">The RAWC kit is available for download from the VMware partner central website. </font></span>

<span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial"></span>

<span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial"></span>

<span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial">\[ad#verticaal\]</span>

<span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial"></span>
