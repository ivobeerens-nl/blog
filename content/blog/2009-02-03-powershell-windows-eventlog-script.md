---
aktt_notify_twitter:
- "no"
author: Ivo Beerens
categories:
- Uncategorized
date: "2009-02-03T20:44:06Z"
guid: http://www.ivobeerens.nl/?p=302
id: 302
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- eventlog
- Powershell
- windows
title: Powershell Windows Eventlog script
url: /2009/02/03/powershell-windows-eventlog-script/
---

This week i found the report-events Powershell script (see figure 1). The script is made by Jeffrey Hicks. It generates a nice HTML file with errors and warnings from the Windows eventlog.

[![image](http://localhost/wp-content/uploads/2009/02/image-thumb.png "image")](http://localhost/wp-content/uploads/2009/02/image.png)

<span style="font-size: xx-small;">figure 1. Output reports-event script</span>

You can specify multiple servers in a text file, select how many hours from the current time to look in the eventlog and e-mail the HTML file after generation.

The following syntax can be used:

> get-content c:\\script\\servers.txt | c:\\scripts\\report-event.ps1 – report c:\\script\\eventlog.html –hours 48 –smtp mail.beerenss.nl –sendto [eventlogs@beerens.nl](mailto:ivo@ivobeerens.nl) –from [eventlog@beerens.nl](mailto:eventlog@ivobeerens.nl)

Explanation:

> get-content c:\\script\\servers.txt, text file containing the server names
> 
> – report c:\\script\\eventlog.html, name of the HTML file
> 
> | c:\\scripts\\report-event.ps1, call the actually script
> 
> –hours 48, hours to report from the curren time
> 
> –smtp mail.beerens.nl. SMTP server to sent the HTML rapport
> 
> –sendto [ivo@beerens.nl](mailto:ivo@ivobeerens.nl), To address
> 
> –from [eventlog@beerens.nl](mailto:eventlog@ivobeerens.nl) . from address

Schedule this script to run frequently to watch your eventlogs!

Download the script [here.](http://jdhitsolutions.com/resources/scripts/Report-Events.txt)

<span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><span><span style="line-height: 150%; mso-bidi-font-size: 11.0pt"><span style="font-size: small; color: #000000; font-family: TheMix B3 Light;"><span style="word-spacing: 0px; text-transform: none; color: #000000; text-indent: 0px; font-family: verdana; white-space: normal; letter-spacing: normal; border-collapse: separate; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0;"> <span style="font-family: Courier New;"><span style="font-family: Courier New;">\[ad#verticaal\]</span></span></span></span></span></span></span>
