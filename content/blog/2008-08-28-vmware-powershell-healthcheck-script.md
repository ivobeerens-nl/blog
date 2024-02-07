---
aktt_notify_twitter:
- "no"
author: Ivo Beerens
categories:
- Powershell
- VMware
date: "2008-08-28T14:57:27Z"
guid: http://www.ivobeerens.nl/?p=106
id: 106
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Powershell
- Snapshot
- VMware
title: VMware Powershell Healthcheck script
url: /2008/08/28/vmware-powershell-healthcheck-script/
---

Healthcheck is a Powershell script that reports information like **snapshots**, **VMware tools version**, **datastore space, CDROM and/or floppy drives connected** etc. to HTML and e-mail the output to a person or distribution list.

**Reason for creating this script:**

As VMware Consultant I see a lot of common problems in VMware environments like:

– Snapshots are enabled and forgot the commit to the VM.

– Datastores are almost full (for example if snapshots are enabled)

– VMware tools versions are different

– CDROM and floppy drives are still mounted to the VM

– Virtual Machines have CPU and Memory limits or reservations (VMs are swapping)

– In the VM, the VMware Tools timesync option is not enabled

In the Virtual Infrastructure Client (VIC) it is difficult to see this sort of information. By creating a Powershell script, I can do a quick inventory. In a lot of VMware environments I created a scheduled tasks, so the script runs once a week and sent to HTML rapport to the administrator.

**What does the script:**

I wrote a Powershell script with HELP from the VMTN community that makes a HTML file and sent the output by e-mail to a person or distribution list. The Healthcheck script does the following checks:

– VMware ESX hardware

– VMware ESX versions

– VMware VirtualCenter versions

– Active snapshots

– CDROM and Floppy drive(s) mounted to the VM

– Datastore information like capacity, free space and the percentage free space

– VirtualMachine (VM) information like VMware tools version, CPU, Memory reservations and limits etc.

– On what VMs VMware Tools timesync is not enabled

**Requirements:**

The following software must be installed:

Microsoft Powershell 1.0 (http://www.microsoft.com/windowsserver2003/technologies/management/powershell/download.mspx)

VMware Infrastucture (VI) toolkit for Windows 1.0

<http://www.vmware.com/download/sdk/>

Set the ExecutionPolicy in Windows Powershell to RemoteSigned by using the following command:

**set-ExecutionPolicy RemoteSigned**

**Installation:**

– Unzip the Healthcheck.zip script to a directory on the VC server for example.

– When the ZIP if unpacked there are two files:

– Healthcheck.ps1, this is the Powershell script

– Style.CSS, controls the HTML layout

**Configuration:**

– Edit the Powershell.ps1 file

edit the following variables:

$vcserver=”localhost”

Enter the VC server, if you execute the script on the VC server you can use the localhost name

$filelocation=”D:\\temp\\Healthcheck.htm”  
Specify the location where to store the HTML output

$enablemail=”yes”  
Enable (yes) or disable (no) to sent the script by e-mail

$smtpServer = “mail.ivobeerens.nl”  
Specify the SMTP server in your network

$mailfrom = “VMware Healtcheck <<powershell@ivobeerens.nl>>”  
Specify the from field

$mailto = <ivo@ivobeerens.nl>

Specify the address where the e-mail to sent to

**Usage:**

Manually run the Healthcheck.ps1 script”:

1\. Open Powershell

2\. Browse to the directory where the Healthcheck.ps1 script resides

3\. enter the command:

./Healthcheck.ps1

To create a schedule task in for example Windows 2003 use the following syntax in the run property:  
Powershell -command “&amp; ‘path\\Healthcheck.ps1’  
edit the path

Powershell -command “&amp; ‘path\\Healthcheck.ps1’

edit the path .

**Future:**

– List Orphaned VMDK’s

– Add performance information like VM usage

– Check timesync on the VMware hosts

Happy testing 🙂

Download Link: Healthcheck script

The script is posted on the VMware Powershell contest forum, [link](http://communities.vmware.com/message/1036432)

Some screenshots of the HTML output:

[![1JPG](http://localhost/wp-content/uploads/2008/08/1jpg-thumb.jpg)](http://localhost/wp-content/uploads/2008/08/1jpg.jpg)

**[![2](http://localhost/wp-content/uploads/2008/08/2-thumb.jpg)](http://localhost/wp-content/uploads/2008/08/2.jpg)**

[![3](http://localhost/wp-content/uploads/2008/08/3-thumb.jpg)](http://localhost/wp-content/uploads/2008/08/3.jpg)

<span style="font-family: Courier New;"><span style="font-family: Courier New;">\[ad#verticaal\]</span></span>
