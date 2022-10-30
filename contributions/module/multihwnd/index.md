---
uid: "contribution/multihwnd"
uid-meta: "contribution/multihwnd-meta"
comments: 
 items: 
  - uid: "52649"
  - uid: "65280"
uid-files: "contribution/multihwnd-files"
title: "multiHWND"
image: "multiHWND showoff.jpg"
contribution: "true"
---

The MultiHWND node allows you to get multiple handles for windows that share the same name.
All you have to do is click all the windows at least once (more may be necessary).

In the zip you will find a precompiled binary and a folder with the dynamic plugin, and a help patch. Choose the folder if you want to tinker with the code, else use the .dll and extract it together with the helppatch to the same location so the helppatch will work on F1.


*note on version 2.0: Rewrite as (dynamic) plugin. Everything is better now: spreadable, dynamically sized handle lists, order and place of the handle in its list is kept (if so desired), more stable, etc. The downside is that it depends (for now - tell me how to fix it) on your windows directory being C:\Windows\... And does anyone need sorting after window position? Because that isn't implemented in this version. I could add it, but I don't need it and you could do that externally afterwards with the Window node.

*note on version 1.2: This version fixes a rather rare bug that occurred when you input a window name after that input had been NIL for some time. Also this version is saved in beta24 (whatever benefits that may bring for you).

*note on version 1.1: Fixes two bugs I had with the output sorting. Now it should cope with Handles for non-existing windows better. Please (re-)download v1.1.