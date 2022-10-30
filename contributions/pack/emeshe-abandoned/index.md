---
uid: "contribution/emeshe-abandoned"
uid-meta: "contribution/emeshe-abandoned-meta"
comments: 
 items: 
  - uid: "106627"
  - uid: "106628"
  - uid: "106629"
  - uid: "106630"
  - uid: "106633"
  - uid: "106638"
  - uid: "106643"
  - uid: "106646"
  - uid: "106649"
  - uid: "106652"
  - uid: "106658"
  - uid: "106902"
  - uid: "106925"
  - uid: "107012"
  - uid: "107029"
  - uid: "107103"
  - uid: "107106"
  - uid: "107236"
  - uid: "107272"
  - uid: "107298"
  - uid: "107687"
  - uid: "107688"
  - uid: "107689"
  - uid: "107844"
  - uid: "107903"
  - uid: "107969"
  - uid: "107976"
  - uid: "108594"
  - uid: "108597"
  - uid: "108623"
  - uid: "108631"
  - uid: "108673"
  - uid: "108836"
  - uid: "109784"
  - uid: "109816"
  - uid: "110110"
  - uid: "110150"
  - uid: "110187"
  - uid: "111435"
  - uid: "111493"
  - uid: "111501"
  - uid: "164300"
  - uid: "164309"
  - uid: "164524"
  - uid: "164525"
  - uid: "166484"
  - uid: "166670"
  - uid: "166794"
  - uid: "167500"
  - uid: "167556"
  - uid: "171131"
  - uid: "171232"
  - uid: "171234"
  - uid: "173014"
  - uid: "173017"
  - uid: "173053"
  - uid: "193954"
  - uid: "193962"
  - uid: "194077"
  - uid: "199789"
  - uid: "199801"
  - uid: "199807"
  - uid: "199873"
  - uid: "200058"
  - uid: "200074"
  - uid: "200098"
  - uid: "207010"
  - uid: "216357"
  - uid: "216366"
  - uid: "217748"
  - uid: "217757"
  - uid: "217758"
  - uid: "218606"
  - uid: "218614"
  - uid: "218627"
  - uid: "218774"
  - uid: "218798"
  - uid: "218831"
  - uid: "219162"
  - uid: "219167"
  - uid: "219511"
  - uid: "223016"
  - uid: "223020"
  - uid: "223023"
  - uid: "223025"
  - uid: "223052"
  - uid: "223081"
  - uid: "225279"
  - uid: "233619"
  - uid: "233620"
  - uid: "233621"
  - uid: "233622"
  - uid: "233624"
  - uid: "233628"
  - uid: "233642"
  - uid: "233643"
  - uid: "233644"
  - uid: "233660"
  - uid: "248051"
title: "Emeshe [ABANDONED]"
image: "Cover.jpg"
contribution: "true"
---

##  ABANDONED!
Emeshe failed in several aspects and I changed my focus a long time ago. It's not maintained for a year now at least and supporting dependencies had many breaking changes since then. I won't revive it either. Check out SuperPhysical or lighting/post-process solutions in mp.dx for alternatives. If you need more graphical fidelity than that use UE4 with the Spout plugin ;)

WARNING! THIS IS A RESOURCE HOG! I'M NOT RESPONSIBLE FOR ANY MOLTEN LAPTOPS!

The great overhaul to mre.mdmod.2 is now here and it's called Emeshe now (for vague reasons)

##  [Get it from Github](https://github.com/microdee/Emeshe)
##  Features
Lighting / Global Illumination
* HDR rendering
* Cook-Torrance and Phong models (Ashikmin-Shirley coming soon)
* Multiple Point, Spot, Sun lights
* Multiple PCSS Shadows for each light types
* Separated light components for versatile composition
* * Diffuse
* * Specular
* * SSS
* Alchemy HBAO for short range Local AO (SSLAO) or High Frequency SSAO
* One-bounce stochastic Local Color Bleeding (CSSGI by ArKano22)
* Environment map based Reflection / Refraction with roughness
* Screen-Space Reflections again with roughness
* Spotlights can have custom texture
* Emission

Post-Processing
* Stochastic "lens blur" DOF with optional "Autofocus"
* Motion Blur with pixel extension in the direction of motion (no hard edges)
* Tonemapping (HDR to SDR)
* * Filmic (Uncharted 2)
* * Filmic (ALU)
* * Reinhard (standard and modified)
* * Drago Logarithmic
* * Standard linear, logarithmic and exponential
* Glare with chromatic aberration

Forward rendering part
* define driven feature switches (opt-out style)
* Optional Triplanar texture coordinates and sampling
* Normal mapping
* Support for automatic and manual instancing
* For manual instancing see Geometry part.
* Rendertarget for UV coordinates, Material ID and Object ID's

Materials
* Flags driven modular deferred material system
* 27 different predefined material features (out of current 32)
* 70+ possible predefined parameters per material and growing
* Texture mapped deferred parameters because UV is written in GBuffer
* Custom features can be added without effort (there's place for 7 custom features)
* VObject Oriented construction in patch

Geometry
* Support for previous frame position for animated geometry (used for calculating velocity map for motion blur)
* Instance or general purpose subset ID written to vertex
* Extruder
* Skinning
* PN-Triangle tessellation
* Compatible with Instance Noodles
* Merged Geometry pipeline for draw-call optimization
* * Subset ID's for individual "slices"
* * Special "MergedGeom" layer sinks for them

##  Installation
* compile DX11 from Github: [DX11-vvvv](https://github.com/mrvux/dx11-vvvv)
* put the mcropack packs into your packs folder: [mcropack](https://github.com/microdee/VVVV.Packs.mcro)
* put VObjects next to mcropack packs: [VObjects](https://github.com/microdee/VObjects)
* put Emeshe next to mcropack packs: [Emeshe](https://github.com/microdee/Emeshe)

Your folder structure should look like:
vvvvdir\packs\
* dx11
* mp.dx
* mp.essentials
* mp.fxh
* mp.voocam
* Emeshe
* VObjects

enjoy!

##  Stuffs
Read more info and somewhat proper docs here: https://github.com/microdee/Emeshe/blob/master/README.md
prezi for NODE15 workshop: http://prezi.com/n3gvyzo9szrw
github: https://github.com/microdee/Emeshe
please report issues here: https://github.com/microdee/Emeshe/issues

enjoy!
