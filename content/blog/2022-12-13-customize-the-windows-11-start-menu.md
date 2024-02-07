---
author: Ivo Beerens
categories:
- Windows 11
date: "2022-12-13T08:37:53Z"
guid: https://www.ivobeerens.nl/?p=8519
id: 8519
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- Start Menu
- Windows 11
title: Customize the Windows 11 Start Menu
url: /2022/12/13/customize-the-windows-11-start-menu/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

Start Menu management in Windows 11 is different than Windows 10. Microsoft recommended an MDM provider such as Microsoft Intune to manage the Windows 11 Start Menu.

[![](http://localhost/wp-content/uploads/2022/12/2startmenu-300x144.jpg)](http://localhost/wp-content/uploads/2022/12/2startmenu.jpg)

There are many environments (such as VDI and Azure Virtual Desktop(AVD) that don’t use an MDM provider to manage their Windows 11 workspace environment. In this blog post, I will highlight how to manage the Start Menu with native tools such as Active Directory and Group Policies.

I will create several blog posts about how to customize the Windows 11 Start Menu, configure the taskbar, remove unwanted desktop icons and remove bloatware and apps.

- **Customize the Windows 11 Start Menu (this blog post)**
- **Customize the Windows 11 Desktop icons**
- **Customize the Taskbar icons**
- **Remove bloatware from the Start Menu**

In this blog post, I will highlight how to customize the Windows 11 Start Menu with native Active Directory Group Policies.

In Windows 10 you can export and import the Start Menu layout. With the “Export-StartLayout” PowerShell command, the Start Menu is exported to an XML file. With a Group Policy, you refer to the custom XML file.

In Windows 11, the Start Menu is exported to a JSON file. The command is like this:

```
Export-StartLayout -Path "C:\Layouts\LayoutModification.JSON"
```

There is no Group Policy (Windows 11 22H2) to import a Start Menu JSON file. The Group Policy only works with an XML file.

There is a workaround. In Windows 11 the Start Menu is stored in a single encrypted file in the following folder location:

```
%LocalAppdata%\Packages\Microsoft.Windows.StartMenuExperienceHost_cw5n1h2txyewy\LocalState
```

In this folder, there is a ***start.bin*** or ***start2.bin*** (depending on the Windows 11 version) file. This file is the Windows 11 Start Menu that can be copied.

These steps will copy the modified Start Menu to a central location and when the endpoint starts the modified Start Menu will be copied to the default user profile. When new users logs in, they will get the customized Start Menu.

- Pin/unpin and organize the apps in the Start Menu the way you want.

[![](http://localhost/wp-content/uploads/2022/12/3_unpin-300x145.jpg)](http://localhost/wp-content/uploads/2022/12/3_unpin.jpg) [![](http://localhost/wp-content/uploads/2022/12/4_startmenu-300x145.jpg)](http://localhost/wp-content/uploads/2022/12/4_startmenu.jpg)

- Create a cmd file called w11startmenu.cmd with the following context:

```
```

- Open Group Policy Management console

[![](http://localhost/wp-content/uploads/2022/12/5_GPO-300x128.jpg)](http://localhost/wp-content/uploads/2022/12/5_GPO.jpg)

All users who log in with a new profile will get the customized Windows 11 Start Menu.

More information can be found in the following article, [link](https://learn.microsoft.com/en-us/windows/configuration/customize-start-menu-layout-windows-11).
