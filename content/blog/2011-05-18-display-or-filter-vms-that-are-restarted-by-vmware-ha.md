---
author: Ivo Beerens
categories:
- HA
- High Availaiblity
- VMware
- vSphere
date: "2011-05-18T22:30:21Z"
guid: http://www.ivobeerens.nl/?p=841
id: 841
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- ha
- high availability
- VMware
- vSphere
title: Display or filter VMs that are restarted by VMware HA
url: /2011/05/18/display-or-filter-vms-that-are-restarted-by-vmware-ha/
---

<font color="#445864">When VMware High Availability(HA) comes in action, the VMs are restarted (depending on the HA settings) on other VMware ESX servers in the cluster. It’s handy to know what VMs are restarted. </font>

<font color="#445864">In the vCenter client the Tasks and Events page size can be increased. Default the vCenter client displays 100 tasks and events. In a cluster with a lot of host and a HA action the 100 tasks and events can be to low. So increasing the size will display the events that list what VMs ate restarted. Increasing can be done by using the following steps:</font>

<font color="#445864">– Open the vCenter client</font>

<font color="#445864">– Choose **Edit**</font>

<font color="#445864">– **Client Settings**</font>

<font color="#445864">– **Lists**</font>

<font color="#445864">– Task and Events, Page size</font>

<font color="#445864">– Increase the value (default value 100)</font>

<font color="#445864">To find the VMs that are restarted click on the cluster, go to events tab and search for the following message:</font>

**<font color="#445864">Virtual machine <VM> was restarted on <host> since <hostname> failed </font>**

<font color="#445864">This is a time consuming task to filter out these messages. </font>

<font color="#445864">An easier and quicker way is to use PowerCLI and use the following one-liner:</font>

| <span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl">001</span><span style="font-family: "Times New Roman","serif"; font-size: 12pt; mso-fareast-language: nl"><font color="#000000"> </font></span> | <span style="font-family: consolas; color: blue; font-size: 10pt; mso-fareast-language: nl">Get-VIEvent</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: darkblue; font-size: 10pt; mso-fareast-language: nl">-MaxSamples</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: fuchsia; font-size: 10pt; mso-fareast-language: nl">500</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: darkgray; font-size: 10pt; mso-fareast-language: nl">\|</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: blue; font-size: 10pt; mso-fareast-language: nl">select</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: fuchsia; font-size: 10pt; mso-fareast-language: nl">FullFormattedMessage</span><span style="font-family: consolas; color: darkgray; font-size: 10pt; mso-fareast-language: nl">,</span><span style="font-family: consolas; color: fuchsia; font-size: 10pt; mso-fareast-language: nl">CreatedTime</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: darkgray; font-size: 10pt; mso-fareast-language: nl">\|</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: blue; font-size: 10pt; mso-fareast-language: nl">Out-GridView</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: "Times New Roman","serif"; font-size: 12pt; mso-fareast-language: nl"></span> |
|---|---|

<font color="#445864">This one-liner displays the last 500 events in a gridview. Filter on the keyword “**restarted**” and all the VMs that are restarted are filtered in the gridview. </font>

[![image](http://localhost/wp-content/uploads/2011/05/image_thumb1.png "image")](http://localhost/wp-content/uploads/2011/05/image1.png)
