---
title: "vRealize Operations Manager error \"javax.naming.NameNotFoundException\""
date: "2015-12-08T12:21:45.000Z"
categories: 
  - "vrealize"
tags: 
  - "vmware"
  - "vrealize"
---

After upgrading vRealize Operations Manager to version 6.1 the Horizon View metrics are not collected anymore. On the Horizon View Connection Server where the vRealize broker agent is installed the following error is displayed in the logs:

> vRealize Operations Manager broker error "javax.naming.NameNotFoundException"
> ERROR   BrokerPoll message sending error: javax.naming.NameNotFoundException: V4V-BrokerMessageServer

The logs can be found in the following location on the Horizon View Connection broker:

\[code language="text"\] c:\\ProgramData\\VMware\\vCenter Operations for View\\logs\\v4v\_broker\_agent\_cfg.... log \[/code\]

To resolve this error you need to restart the collector service on the vRealize Operations Manager Appliance. Run the following steps:

- Open a console session on of the vRealize Operations Manager collector node (SSH is disabled by default)
- Press ALT- F1 in the console session
- Log in as root user with no password
- Change the password the first time
- Restart the collector service by using the following command:

\[code language="powershell"\] service vmware-vcops restart collector \[/code\]

It can take serveral minutes to pair the Broker Agent with the Horizon View adapter.

The SSH Service on the vRealize Operations Manager Appliance is disabled by default. To enable and start the SSH service use the following commands:

- Start the SSH service

\[code language="powershell"\] service sshd start \[/code\]

- To configure SSH to start automatically

\[code language="powershell"\] chkconfig sshd on \[/code\]

- Check the status of the SSH service

\[code language="powershell"\] chkconfig \[/code\]

[![2015-12-08_12h55_01](images/2015-12-08_12h55_01-300x102.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/12/2015-12-08_12h55_01.png)
