---
uid: "contribution/vioso-vwf-calibration-loader"
uid-meta: "contribution/vioso-vwf-calibration-loader-meta"
comments: 
 items: 
  - uid: "225796"
  - uid: "225804"
  - uid: "225816"
  - uid: "225817"
  - uid: "225819"
uid-files: "contribution/vioso-vwf-calibration-loader-files"
title: "Vioso vwf calibration Loader"
image: "Capture_0.JPG"
contribution: "true"
---

This plugin loads the info from any <www.vioso.com> calibration software (vioso player, calibrator or Wings ) .vwf 

Basically gets the 2 textures, one for warping and another for soft-edge blending.


It really has a lot to improve... maybe someone with more experience can help... this is just a prototype, Im sure there's better ways to read the raw data.


Since the warp texture is 128bit, for big .vwf files only works on x64

The DX11ToDX9 texture is sending a 16bit texture.

**Needs dx11 and VVVV x64**



1.  ToDo:
-Spreadable read of the raw data and display info

-All ported to dx11

-Add it to the VVVV-Dome maybe?





1.  DOWNLOAD .vwf sample file HERE: 
<https://www.dropbox.com/s/yo4qhhfmru5bc3a/warp%202x3840x2400.vwf?dl=0>