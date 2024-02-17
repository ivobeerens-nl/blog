---
author: Ivo Beerens
categories:
- Uncategorized
date: "2018-10-24T20:32:04Z"
guid: https://www.ivobeerens.nl/?p=6339
id: 6339
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_reddit_counts:
- "5"
ssb_total_counts:
- "7"
tags:
- VDI
- windows 10
title: What Windows 10 version for my VDI desktop?
url: /2018/10/24/what-windows-10-version-for-my-vdi-desktop/
---

In a VDI project one of the questions in the design phase is always: “What version I use for my Windows 10 VDI desktop?”. Before Windows 10, the Operating System release cycle was approximate 3 to 5 years. With Windows 10 a new release management concept is introduced called “Windows as a Service (WaaS)”. WaaS includes:

- **Feature updates**: Twice a year new feature updates to Windows 10 will be released
- **Quality updates**: Deliver both security and non-security fixes every month on patch Tuesday such as: 
    - Security updates
    - Critical updates
    - Servicing stack updates
    - Driver Updates
- **Servicing channels**: Allow organizations to choose when to deploy new features. The following channels are available: 
    - **Semi-Annual Channel (SAC)**: This is also known as the Current Branch. Receive feature updates twice a year (Around March and September/October) with a 18/30 months support cycle. SAC releases numbers are for example: 1703, 1709, 1803 and 1809. (1809 stands for 18 = 2018, 09 = September).
    - **Long Term Servicing Branch (LTSB) that is now called the Long Term Servicing Channel (LTSC)**. LTSC shares the same codebase as Windows 10 IoT and is only available when having a Windows 10 Enterprise license. The typical use cases are embedded systems such as manufacturing or medical equipment and KIOSK systems that don’t run Office and receive new feature updates every 2 to 3 years. LTSC comes with 10 years support cycle and looks like an Operating System release cycle before Windows 10 such as Windows 7 for example. The new announced LTSC version is called: Windows 10 2019 LTSC build 1809.
- **Deployment rings**: are groups of devices used to initially pilot, and then to broadly deploy, each feature update in an organization

So we can choose between two servicing channels. Here is a quick comparison table between the two channels:

|  | **LTSB/LTSC** | **Semi-Annual Channel (SAC)** |
|---|---|---|
| Support | 10 years | 18/30 months (Windows 10 Support lifecycle, [link](https://support.microsoft.com/en-us/help/13853/windows-lifecycle-fact-sheet).) |
| Latest new features or security enhancements | No | Yes |
| Support for new hardware (silicon) and Surface | No | Yes |
| Default browser(s) | Internet Explorer 11 | Internet Explorer 11, Microsoft Edge |
| Office | LTSC only supports Office 2019. On January 14, 2020 , Office 365 ProPlus will be no longer supported on LSTC or the older LTSB version ([link](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Changes-to-Office-and-Windows-servicing-and-support/ba-p/151509)) | Yes |
| Updates and Security updates | Yes | Yes |
| Office support | Yes | Yes |
| Universal Apps Support | Yes | Yes |
| Cortana support | No | Yes |
| Windows Store | No | Yes |
| Windows Ink and MS camera support | No | Yes |
| Includes non-business apps like Xbox, Minecraft, Candy crush | No | Yes |
| ConfigMgr Express Update | No | Yes |
| OneNote OneDrive files on demand that is introduced in release 1709 is not included in LTSB 1607. | No | Yes |

The advice from Microsoft is to use SAC channel over a LTSB/LTSC channel. Ask yourself the question: **Why do I use a Windows OS? My personal answer on this question is: Because I need to run legacy Windows apps.** So a stable OS that requires less patching and overhead can be more relevant than having the latest features which involves more management, testing and overhead. But more and more customers are migrating to Office 365. Office 365 ProPlus delivers cloud-connected and always up-to-date versions of Office desktop apps. This requires Windows Update OS requirements for Office 365 ProPlus which means you’re stuck with the SAC channel.

For choosing between the Professional and the Enterprise edition there is a comparison table available [link](https://www.microsoft.com/en-us/windowsforbusiness/compare). Windows 10 Enterprise has for example more advanced security and management functions and support for LTSC.

When deciding what channel and Windows 10 version release to use, ask yourself the following questions:

- Define the business scope, requirements, constrains, assumptions and risks.
- What Windows 10 versions are supported by my VDI brokers and software such as Citrix XenDesktop, VMware Horizon, App Volumes and NVIDIA for example?
- Are we going to use Office 365?
- Do my applications support the channel and version? Ask the software vendors.
- Define a update and patch management plan.
- Perform a Proof of Concept (PoC).

I hope this blog post makes it easier to choose the right Windows 10 version for the VDI desktop.
