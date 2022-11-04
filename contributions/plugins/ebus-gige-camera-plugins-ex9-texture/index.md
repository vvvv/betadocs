---
uid: "contribution/ebus-gige-camera-plugins-(ex9.texture)"
uid-meta: "contribution/ebus-gige-camera-plugins-(ex9.texture)-meta"
comments: 
 items: 
  - uid: "233290"
  - uid: "233419"
  - uid: "274806"
uid-files: "contribution/ebus-gige-camera-plugins-(ex9.texture)-files"
title: "eBus GigE Camera Plugins (ex9.Texture)"
contribution: "true"
---

comes as a package of three plugins and one helppatch: 

- ListDevices 
- VideoCapture (ex9)
- SetFeature

uses PvDotNet.dll of [Pleora's ebus SDK](http://www.pleora.com/our-products/ebus-sdk) - didn't quite understand if it actually supports all GenICam and gigE devices, but there's a chance...

dll's should work as drag'n'drop into your project. Requires the eBus drivers to be installed!

Still needs some cleaning and optimizing (on average one frame drops every three hours).
Tested with multiple Flir Thermal Cameras - one Capture Node for each Camera required though.

developed at [StruktStudio](http://strukt.com)
source code will be put on [github](https://github.com/struktstudio) once we find time to clean it a little - some things seem overly complicated...
