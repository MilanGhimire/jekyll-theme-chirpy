---
title: Error starting Apache in windows where IIS is also installed
author: Milan Ghimire
date: 2020-06-10 20:55:05 +05:45
categories: []
tags: [untaged]
---


I got this error:
```shell
1:34:34 PM  [Apache] 	Error: Apache shutdown unexpectedly.
1:34:34 PM  [Apache] 	This may be due to a blocked port, missing dependencies, 
1:34:34 PM  [Apache] 	improper privileges, a crash, or a shutdown by another method.
1:34:34 PM  [Apache] 	Press the Logs button to view error logs and check
1:34:34 PM  [Apache] 	the Windows Event Viewer for more clues
1:34:34 PM  [Apache] 	If you need more help, copy and post this
1:34:34 PM  [Apache] 	entire log window on the forums
```

It is because the IIS is running in port 80,
to solve 
Run CMD as administrator and type:
```terminal
net stop was /y
```