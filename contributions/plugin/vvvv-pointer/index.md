---
uid: "contribution/vvvv.pointer"
uid-meta: "contribution/vvvv.pointer-meta"
comments: 
 items: 
  - uid: "275910"
  - uid: "277596"
  - uid: "278213"
  - uid: "278215"
uid-files: "contribution/vvvv.pointer-files"
title: "VVVV.Pointer"
contribution: "true"
---

a couple of years late here comes the [ms](https://docs.microsoft.com/en-us/windows/win32/inputmsg/wmpointer-reference) recommended way (since windows 8) for handling **mouse, touch and pen input** with proper **gesture handling** and **touch injection**.

the touch and gesture APIs actually use this unified api windows internally anyways so performance should be at least on par.

##  benefits over the existing implementations
* touch and gesture are not mutually exclusive anymore
* gestures can be used with mouse or pen input as well
* **unified interface** means no more building your own input object and switch between mouse and touch when developing.
* touch **injection** lets you simulate multitouch systemwide. (beware, it will take over your cursor!)
* fine grained control over gestures: specify type (translation, scale & rotation), allowed axis & inertia params
* gesture takes care for you, whether it's a gesture or a (double)tap/click