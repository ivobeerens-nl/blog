---
title: "VMware tools update fails on ESXi 6 hosts with Dutch Operating System VMs"
date: "2015-05-04T09:35:04.000Z"
categories: 
  - "esxi"
  - "VMware"
tags: 
  - "esxi-2"
  - "VMware"
  - "VMware-horizon-view"
author: Ivo Beerens
---

> VMware Tools Setup Wizard ended prematurely

[![VMware tools](images/VMware-tools-300x234.png)](images/VMware-tools.png)

This is a known bug in VMware ESXi 6.0 with Dutch Operating System VMs (see KB, [link](http://kb.VMware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2114476)).

The following work around can be used:

- Create a local group named "everyone"
- Add the user used for installing VMware tools to the "everyone" group
- Run the VMware tools upgrade
- Remove the "everyone" group



