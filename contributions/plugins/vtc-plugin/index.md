---
uid: "contribution/vtc-plugin"
uid-meta: "contribution/vtc-plugin-meta"
comments: 
 items: 
  - uid: "51577"
  - uid: "51581"
  - uid: "51582"
uid-files: "contribution/vtc-plugin-files"
title: "VTC Plugin"
image: "vtc.png"
contribution: "true"
---

Here's a little plugin i've been working on. I've always wanted to interface the good old VT Controller (pictured above) to vvvv since i've seen some japanese dude do some vjing with it in [this video](http://www.youtube.com/watch?v=dt-1QCFEnBE).
There's been a [Windows HID driver](http://www.tamanegi.org/prog/vtchid/) available for this device for a long time, but unfortunately it's only available as an x86 build. So i built a new winusb based driver with the very nice libusbdotnet and a matching vvvv plugin to call it. If anybody has one of these collecting dust somewhere now is probably the time to get it out and have some good, clean x86/x64 fun!
also this plugin may serve as a sample for libusbdotnet-based plugins to interface other devices.