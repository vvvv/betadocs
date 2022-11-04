---
uid: "contribution/superphysical"
uid-meta: "contribution/superphysical-meta"
comments: 
 items: 
  - uid: "231293"
  - uid: "231346"
  - uid: "231424"
  - uid: "232217"
  - uid: "232483"
  - uid: "232939"
  - uid: "233289"
  - uid: "233300"
  - uid: "235174"
  - uid: "235176"
  - uid: "235183"
  - uid: "235184"
  - uid: "235185"
  - uid: "235354"
  - uid: "235362"
  - uid: "235363"
  - uid: "235447"
  - uid: "236898"
  - uid: "237474"
  - uid: "238464"
  - uid: "238542"
  - uid: "240057"
  - uid: "240431"
  - uid: "241361"
  - uid: "241364"
  - uid: "241371"
  - uid: "241374"
  - uid: "241495"
  - uid: "241625"
  - uid: "241715"
  - uid: "241768"
  - uid: "241866"
  - uid: "241994"
  - uid: "242038"
  - uid: "242767"
  - uid: "242799"
  - uid: "242818"
  - uid: "242823"
  - uid: "243390"
  - uid: "244770"
  - uid: "246913"
  - uid: "246915"
  - uid: "247044"
  - uid: "247879"
  - uid: "248665"
  - uid: "248668"
  - uid: "248670"
  - uid: "248699"
  - uid: "248770"
  - uid: "248772"
  - uid: "248776"
  - uid: "248792"
  - uid: "248793"
  - uid: "248799"
  - uid: "248802"
  - uid: "248803"
  - uid: "248832"
  - uid: "248852"
  - uid: "249229"
  - uid: "249267"
  - uid: "251147"
  - uid: "251196"
  - uid: "251658"
  - uid: "251738"
  - uid: "251909"
  - uid: "251923"
  - uid: "251924"
  - uid: "251926"
  - uid: "253913"
  - uid: "253945"
  - uid: "254917"
  - uid: "254919"
  - uid: "256363"
  - uid: "256398"
  - uid: "257098"
  - uid: "257112"
  - uid: "257113"
  - uid: "257144"
  - uid: "257145"
  - uid: "261053"
  - uid: "261055"
  - uid: "270758"
  - uid: "270760"
  - uid: "271144"
  - uid: "271149"
  - uid: "271268"
  - uid: "271879"
  - uid: "273481"
  - uid: "273524"
  - uid: "273526"
  - uid: "273538"
  - uid: "273661"
  - uid: "273691"
  - uid: "273933"
  - uid: "274028"
  - uid: "274034"
  - uid: "274066"
  - uid: "274068"
uid-files: "contribution/superphysical-files"
title: "SuperPhysical"
image: "SuperPhysical_0.png"
contribution: "true"
---

SuperPhysical is a forward rendering setup and the successor of SuperPhong.
It features cook-torrance shading, physically based rendering and image based lighting.
The implementation is mainly based on <https://learnopengl.com/#!PBR/Theory>
"focusing on the PBR approach as originally explored by Disney and adopted for real-time display by Epic Games".

Some Features:
* Physical Based Rendering
* Metalness workflow compatible to Substance Designer etc.
* Image Based Lighting
* VSM Shadows
* Image Based Refraction
* Parrallax Occlusion Mapping


Update 2.0:

* Completely overhauled material and light setup powered by custom VL datatypes
* New shadow mapping techniques: Exponential Shadow Maps (ESM) and Postfiltered VSM with varying penumbra size
* Integrated volumetrics
* Lot's of fixes and performance improvements

Installation:
**Put the contribution into packs. Check out SuperPhysical help patch for usage scenario.**
**Compatible from Beta 36!**
All feedback welcome! Have fun!

https://github.com/michael-burk/SuperPhysical

**Deferred version needs DX11 pack version 1.3.1.1.**
Built can be found here:
https://www.dropbox.com/s/q62fefiwho5d2am/DX11andDX11girlpower.zip?dl=0