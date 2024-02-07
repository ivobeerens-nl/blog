---
author: Ivo Beerens
categories:
- exchange
- outlook
date: "2011-03-04T14:11:17Z"
guid: http://www.ivobeerens.nl/?p=780
id: 780
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- exchange
- outlook
title: Reset the Microsoft Outlook folder language
url: /2011/03/04/reset-the-microsoft-outlook-folder-language/
---

<font color="#000000">During a Microsoft Exchange (Exchange 2007 to Exchange 2007) migration between to organizations, I discovered that some mailboxes had an English folder structure in MS Outlook instead of a Dutch. After the mailbox is exported and imported using the export- and import-mailbox command, the users starts the Microsoft Outlook 2007 (Dutch). Microsoft Outlook 2007 creates the default leading Outlook folder structure in Dutch language such as “Postvak In”and “Agenda”. When the imported PST file contains an English Microsoft Outlook folder structure is also exist in the mailbox, but are not the leading default folders. So the mailbox contains folders as “Inbox” and “Postvak In”. For example the “Inbox” contains all the mail and the “Postvak IN” folder is empty and the default leading folder in Outlook. This can be very confusing and give problems such as syncing the mobile device. </font>

<font color="#000000">There is a Outlook command line switch that resets default folder names (such as Inbox or Sent Items ) to default names in the current Office user interface language. The syntax is:</font>

**<font color="#000000">outlook.exe /resetfoldernames</font>**

<font color="#000000">The Outlook command line switch /resetfoldernames didn’t work in this situation. To solve this problem I did a inventory on all the mailboxes who had an folder named “Inbox” at the Exchange 2007 organization where to migrate **from** by executing the the following Powershell script in EMS:</font>

<font color="#000000"></font>

| <div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #cecece; font-size: ; padding-top: 5px"><font face="Consolas"><font style="font-size: 10pt">001</font></font> </div> | <div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #fcfcfc; font-size: ; padding-top: 5px"><font face="Consolas"><span style="color: "><font color="#0000ff"><font style="font-size: 10pt">Get-Mailbox</font></font></span><font style="font-size: 10pt"><span style="color: "> </span><span style="color: "><font color="#00008b">-ResultSize</font></span><span style="color: "> </span><span style="color: "><font color="#ff00ff">Unlimited</font></span><span style="color: "> </span><span style="color: "><font color="#a9a9a9">\|</font></span><span style="color: "> </span></font></font></div><div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #fcfcfc; font-size: ; padding-top: 5px"><font face="Consolas"><font style="font-size: 10pt"><span style="color: "></span><span style="color: "><font color="#0000ff">Get-MailboxFolderStatistics</font></span><span style="color: "> </span><span style="color: "><font color="#a9a9a9">\|</font></span><span style="color: "> </span><span style="color: "><font color="#0000ff">where</font></span><span style="color: "> </span><span style="color: ">{</span><span style="color: "><font color="#ff0000">$\_</font></span><span style="color: "><font color="#a9a9a9">.</font></span><span style="color: ">name</span><span style="color: "> </span><span style="color: "><font color="#a9a9a9">-eq</font></span><span style="color: "> </span><span style="color: "><font color="#8b0000">"Inbox"</font></span><span style="color: ">}</span><span style="color: "> </span><span style="color: "><font color="#a9a9a9">\|</font></span><span style="color: "> </span></font></font></div><div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #fcfcfc; font-size: ; padding-top: 5px"><font face="Consolas"><font style="font-size: 10pt"><span style="color: "></span><span style="color: "><font color="#0000ff">Select</font></span><span style="color: "> </span><span style="color: "><font color="#ff00ff">identity</font></span><span style="color: "><font color="#a9a9a9">,</font></span><span style="color: "> </span><span style="color: "><font color="#ff00ff">folderpath</font></span><span style="color: "> </span><span style="color: "><font color="#a9a9a9">\|</font></span><span style="color: "> </span><span style="color: "><font color="#0000ff">export-csv</font></span><span style="color: "> </span><span style="color: "><font color="#ff00ff">c:\\temp\\inbox.csv</font></span><span style="color: "> </span><span style="color: "><font color="#00008b">-NoTypeInformation</font></span> </font></font></div> |
|---|---|

<font color="#000000">The output with all the mailboxes containing a “inbox” Outlook folder is written to the inbox.csv file. </font>

<font color="#000000">The company Amrein Engineering has an cool utility called [Outlook set folder language.](http://www.amrein.com/download/OLFoLang.zip)</font><font color="#000000"> With this utility you can rename **multiple** Mailbox Outlook folder(s) to another language such as: <span class="body">German, French, English, Italian, Spanish, Dutch, Danish, and Swedish. </span></font>

<span class="body"><font color="#000000">For all the mailboxes I created a custom attribute and added them to the custom address list by filtering on the the custom attribute. In the Outlook set folder language utility I selected the custom address list, selected all the mailboxes, choose as language “Dutch” and hit the Set button. </font></span>

<span class="body"><font color="#000000"></font></span>

<span class="body"><font color="#000000"></font></span>

<font color="#000000"></font>

<span class="body"><font color="#000000"></font></span>

<span class="body">[<font color="#000000">![2011-03-03 14h04_48](http://localhost/wp-content/uploads/2011/03/2011-03-03-14h04_48_thumb.jpg "2011-03-03 14h04_48")</font>](http://localhost/wp-content/uploads/2011/03/2011-03-03-14h04_48.jpg)</span>

<font color="#000000">Within a short period all the mailbox folders were reset to the Dutch language at the Exchange organization were to migrate from. Now I could export and import all the mailboxes to the other Exchange Organization knowing that that every mailbox has the right Outlook folders language structure.</font>

<font color="#000000">I want to thank everybody who helped me with this nasty problem. </font>

<font color="#000000"></font>

<font color="#000000"></font>
