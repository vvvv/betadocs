---
uid: "contribution/filestream-(vlc)-for-dx11"
uid-meta: "contribution/filestream-(vlc)-for-dx11-meta"
comments: 
 items: 
  - uid: "241603"
  - uid: "241623"
  - uid: "241633"
  - uid: "241634"
  - uid: "241682"
  - uid: "244829"
uid-files: "contribution/filestream-(vlc)-for-dx11-files"
title: "Filestream (VLC) for DX11"
contribution: "true"
---

**Filestream (VLC) for DX11**

Same as Filestream (VLC) but with full network streaming capability + support to choose the audio output

Now you can use all the functionality from the Filestream (VLC) node easily together with Vux's DX11 pack,
including network streaming (rtp, rtsp, udp etc.).
Also, you have the possibility to choose the audio out device (per slice).

**Usage:**
Drag the dll + the "libvlc_searchpath.txt" into you project folder
You need to have [DX11 Pack](/contribution/directx11-nodes) and [vlc](http://www.videolan.org/) > 2.0 installed. For x64 you need the VLC Player x64 (little tricky to find at videolan.org).

The output sound device is bounded to the file when you change the filename. For changing the audio output you have to reset the filename after changing the output device.
(check inspector for hidden features like video resolution)