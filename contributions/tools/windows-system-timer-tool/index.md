---
uid: "contribution/windows-system-timer-tool"
uid-meta: "contribution/windows-system-timer-tool-meta"
comments: 
 items: 
  - uid: "112935"
  - uid: "112940"
  - uid: "205251"
  - uid: "228166"
  - uid: "228342"
  - uid: "228520"
  - uid: "230228"
  - uid: "230934"
  - uid: "230935"
  - uid: "230963"
uid-files: "contribution/windows-system-timer-tool-files"
title: "Windows System Timer Tool"
image: "TimerTool_0.png"
contribution: "true"
---

Little tool to check and modify the windows system timer.

If you want to know what this is about, you should read this article:
[Windows Timer Resolution: Megawatts Wasted](http://randomascii.wordpress.com/2013/07/08/windows-timer-resolution-megawatts-wasted/)

The matter is in my opinion less dramatic as the author of the article states, but he has written down a comprehensive collection of facts about the windows timer. Excellent article!

Source code is here: <https://github.com/tebjan/TimerTool>

Verison 3 minimizes to system tray and can be started with command line arguments "-t peroidVal" and "-minimized". e.g. put a .bat file into your autostart with the following code:

```
start "" "C:\PathToTool\TimerTool.exe" -t 0.5 -minimized
exit
```

Version 2 can set 0.5 ms as timer resolution.

If you like it: [Donate some dev bucks](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=2DNX2JBBKED8Q), thanks a lot!