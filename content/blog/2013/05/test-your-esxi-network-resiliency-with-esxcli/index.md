---
title: "Test your ESXi network resiliency with ESXCLI"
date: "2013-05-01T08:12:39.000Z"
categories: 
  - "esxi"
  - "networking"
  - "vSphere"
tags: 
  - "esxi-2"
  - "networking"
  - "vSphere"
author: Ivo Beerens
---

First log in to ESXi using for example using Tech Support Mode

- Get a overview of the installed vmnics

esxcli network nic list

- Bring a vmnic down

esxcli network nic down –n vmnicNumber

- Bring a vmnic up

esxcli network nic up –n vmnicNumber

Only auto-negotiation 10Mb/100Mb/1000Mb/10000Mb speeds vmnics are supported. FlexNics with different speed are not supported.



