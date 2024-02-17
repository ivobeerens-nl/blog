---
title: "Display or filter VMs that are restarted by VMware HA"
date: "2011-05-18T20:30:21.000Z"
categories: 
  - "ha"
  - "high-availaiblity"
  - "vmware"
  - "vsphere"
tags: 
  - "ha-2"
  - "high-availability"
  - "vmware"
  - "vsphere"
---

When VMware High Availability(HA) comes in action, the VMs are restarted (depending on the HA settings) on other VMware ESX servers in the cluster. It’s handy to know what VMs are restarted.

In the vCenter client the Tasks and Events page size can be increased. Default the vCenter client displays 100 tasks and events. In a cluster with a lot of host and a HA action the 100 tasks and events can be to low. So increasing the size will display the events that list what VMs ate restarted. Increasing can be done by using the following steps:

\- Open the vCenter client

\- Choose **Edit**

\- **Client Settings**

\- **Lists**

\- Task and Events, Page size

\- Increase the value (default value 100)

To find the VMs that are restarted click on the cluster, go to events tab and search for the following message:

**Virtual machine <VM> was restarted on <host> since <hostname> failed**

This is a time consuming task to filter out these messages. 

An easier and quicker way is to use PowerCLI and use the following one-liner:

<table style="width: 1.5pt; mso-cellspacing: 0cm; mso-yfti-tbllook: 1184; mso-padding-alt: 3.75pt 3.75pt 3.75pt 3.75pt" class="MsoNormalTable" border="0" cellspacing="0" cellpadding="0" width="2"><tbody><tr style="mso-yfti-irow: 0; mso-yfti-firstrow: yes; mso-yfti-lastrow: yes"><td style="border-bottom-color: #f0f0f0; padding-bottom: 3.75pt; background-color: transparent; border-top-color: #f0f0f0; padding-left: 3.75pt; padding-right: 3.75pt; border-right-color: #f0f0f0; border-left-color: #f0f0f0; padding-top: 3.75pt" valign="top"><p style="margin: 0cm 0cm 0pt; background: #cecece" class="MsoNormal"><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl">001</span><span style="font-family: &quot;Times New Roman&quot;,&quot;serif&quot;; font-size: 12pt; mso-fareast-language: nl"><font color="#000000"></font></span></p></td><td style="border-bottom-color: #f0f0f0; padding-bottom: 3.75pt; background-color: transparent; border-top-color: #f0f0f0; padding-left: 3.75pt; padding-right: 3.75pt; border-right-color: #f0f0f0; border-left-color: #f0f0f0; padding-top: 3.75pt" valign="top" nowrap="nowrap"><p style="margin: 0cm 0cm 0pt; background: #fcfcfc" class="MsoNormal"><span style="font-family: consolas; color: blue; font-size: 10pt; mso-fareast-language: nl">Get-VIEvent</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: darkblue; font-size: 10pt; mso-fareast-language: nl">-MaxSamples</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: fuchsia; font-size: 10pt; mso-fareast-language: nl">500</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: darkgray; font-size: 10pt; mso-fareast-language: nl">|</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: blue; font-size: 10pt; mso-fareast-language: nl">select</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: fuchsia; font-size: 10pt; mso-fareast-language: nl">FullFormattedMessage</span><span style="font-family: consolas; color: darkgray; font-size: 10pt; mso-fareast-language: nl">,</span><span style="font-family: consolas; color: fuchsia; font-size: 10pt; mso-fareast-language: nl">CreatedTime</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: darkgray; font-size: 10pt; mso-fareast-language: nl">|</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"> </span><span style="font-family: consolas; color: blue; font-size: 10pt; mso-fareast-language: nl">Out-GridView</span><span style="font-family: consolas; color: black; font-size: 10pt; mso-fareast-language: nl"></span><span style="font-family: &quot;Times New Roman&quot;,&quot;serif&quot;; font-size: 12pt; mso-fareast-language: nl"></span></p></td></tr></tbody></table>

This one-liner displays the last 500 events in a gridview. Filter on the keyword “**restarted**” and all the VMs that are restarted are filtered in the gridview.

[![image](images/image_thumb1.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/05/image1.png)
