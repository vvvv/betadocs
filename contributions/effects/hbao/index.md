---
uid: "contribution/hbao "
uid-meta: "contribution/hbao -meta"
comments: 
 items: 
  - uid: "253922"
  - uid: "253923"
  - uid: "253925"
  - uid: "253927"
  - uid: "253941"
  - uid: "253942"
  - uid: "253944"
  - uid: "253947"
  - uid: "253948"
  - uid: "253956"
  - uid: "253957"
  - uid: "253959"
  - uid: "254148"
  - uid: "254285"
  - uid: "254313"
  - uid: "254317"
  - uid: "255141"
  - uid: "255243"
  - uid: "255266"
  - uid: "261896"
  - uid: "269024"
  - uid: "269149"
  - uid: "269250"
  - uid: "269253"
  - uid: "269269"
  - uid: "269840"
  - uid: "272937"
uid-files: "contribution/hbao -files"
title: "HBAO+"
image: "vvvvhbaoplus.png"
contribution: "true"
---

HBAO+ is a high effiency screen-space ambient occlusion (SSAO) algorithm developed by NVIDIA.
This is a direct port for the vvvv dx11 pipeline by vux, made by exposing managed vvvv dx11 into native C++ dx11.

###  features
* quite fast
* lots of pins (some hidden), exposes nearly all options of the NVIDIA library
* help patch, including explanations for every pin
* based on HBAO+ 4.0

###  not done (yet?)
* including your own normal buffer (rendering AO on normal maps)
* dual layer depth input to remove halo artifacts

###  installation
* make sure your dx11 pack is version >= 1.2
* drop it into your packs folder

###  source & license
Source is available at: 
<https://github.com/dboleslawski/VVVV.HBAOPlus>
In case any bugs show up, please report them here: 
<https://github.com/dboleslawski/VVVV.HBAOPlus/issues>

Wrapper & Nodes use the MIT license
HBAO+ is licensed via the **GameWorks Binary SDK EULA**  <https://developer.nvidia.com/gameworks-sdk-eula>

