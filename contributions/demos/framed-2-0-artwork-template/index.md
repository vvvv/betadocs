---
uid: "contribution/framed-template"
uid-meta: "contribution/framed-template-meta"
comments: 
 items: 
  - uid: "190699"
  - uid: "190742"
  - uid: "190801"
  - uid: "190822"
  - uid: "191872"
  - uid: "191929"
  - uid: "191959"
  - uid: "191987"
uid-files: "contribution/framed-template-files"
title: "Framed*2.0 Artwork Template"
image: "FramedTemplateContributionImage2.png"
contribution: "true"
---

This is how to prepare your Artwork for the Framed device.

1) Download the Templates
2) Choose between either DX9 or DX11
3) The root patch started by the Framed is: main.v4p
4) Every Artwork must be packed in a ZIP with a "main.v4p" in the root. The remaining folder structure is up to you.
5) Target: **vvvv50_beta35.5_x86 + addonpack + DX11 Pack 1.0.1**

The Framed will run your Renderer fullscreen by using the  "/fullscreen 1" commandline parameter. The Framed (Devices) module (part of this template) takes care of this.

When creating your patches please keep the rather low hardware specifications of the device in mind. The demo coming with this template runs at ~60fps. Note, that Antialiasing of the Renderer is deliberately set to the minimum to gain such performance.
 
## Framed 2.0 Device Specifications
* Intel(R) Atom(TM) CPU  Z3770  @ 1.46GHz (4 CPUs), ~1.5GHz
* Memory: 4096MB RAM
* Windows Embedded 8.1
* Intel(R) HD Graphics
**Native Mode: 1080 x 1920 (portrait) (60Hz)
**Display Memory: 1513 MB
**Dedicated Memory: 32 MB
**Shared Memory: 1481 MB
* Speakers (Intel SST Audio Device (WDM))
* Microphone (Intel SST Audio Device (WDM))
* HD Camera 720p

More info at: 
* http://frm.fm
* [FRAMED 2.0 Guide](https://github.com/frmfm/FRAMED-2.0-Guide)