---
author: Ivo Beerens
categories:
- Windows
date: "2019-01-03T08:55:35Z"
guid: https://www.ivobeerens.nl/?p=6527
id: 6527
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- windows
title: Extend the evaluation period of Windows Server 2012/2016 and 2019
url: /2019/01/03/extend-the-evaluation-period-of-windows-server-2012-2016-and-2019/
---

In my lab environment I use evaluation versions of Windows Server 2012, 2016 and 2019 (if available). The evaluation versions of Windows Server are valid for 180 days by default and can be extended. The Windows Server evaluation versions can be found on the Evaluation Center, [link](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server).

In this example below, the Windows Server 2016 evaluation has only 10 days remaining .

[![](http://localhost/wp-content/uploads/2019/01/1-1-300x182.png)](http://localhost/wp-content/uploads/2019/01/1-1.png) [![](http://localhost/wp-content/uploads/2019/01/2-2-300x116.png)](http://localhost/wp-content/uploads/2019/01/2-2.png)

To extend the evaluation period the following steps can be used:

- - Open an elevated command prompt (cmd)
    - Enter the following command:
 
 ```
[code language="text"]cscript.exe %windir%\system32\slmgr.vbs /dlv[/code]
```

[![](http://localhost/wp-content/uploads/2019/01/3-300x181.png)](http://localhost/wp-content/uploads/2019/01/3.png)

- 
 
- - - There are 6 remaining rearms available. This means the Windows Server evaluation version can be used for 3 years. To rearm use the following command:
 
 ```
[code language="text"]cscript.exe %windir%\system32\slmgr.vbs /rearm[/code]
```

- - Restart the system
    - After the restart the evaluation period is extended for another 180 days
