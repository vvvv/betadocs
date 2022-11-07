---
uid: "contribution/obsolete-see-dx11-pack-kinect2-nodes"
uid-meta: "contribution/obsolete-see-dx11-pack-kinect2-nodes-meta"
comments: 
 items: 
  - uid: "110851"
  - uid: "110852"
  - uid: "110906"
  - uid: "111498"
  - uid: "112187"
  - uid: "112789"
  - uid: "112791"
  - uid: "113687"
  - uid: "151803"
  - uid: "151805"
  - uid: "151808"
  - uid: "152890"
  - uid: "152892"
  - uid: "153738"
  - uid: "153791"
  - uid: "154317"
  - uid: "154323"
  - uid: "154325"
  - uid: "154725"
  - uid: "154726"
  - uid: "154731"
  - uid: "154746"
  - uid: "154793"
  - uid: "155663"
  - uid: "155949"
  - uid: "156656"
  - uid: "157926"
  - uid: "159708"
  - uid: "159709"
  - uid: "159714"
  - uid: "159767"
  - uid: "159873"
  - uid: "159887"
  - uid: "160049"
  - uid: "160052"
  - uid: "160070"
  - uid: "160286"
  - uid: "160313"
  - uid: "160438"
  - uid: "160614"
  - uid: "160618"
  - uid: "160868"
  - uid: "160874"
  - uid: "160876"
  - uid: "161411"
  - uid: "161426"
  - uid: "161831"
  - uid: "161839"
  - uid: "162128"
  - uid: "164305"
  - uid: "169142"
  - uid: "170047"
  - uid: "170172"
  - uid: "170197"
  - uid: "170417"
  - uid: "170419"
  - uid: "171125"
  - uid: "173768"
  - uid: "173772"
  - uid: "173813"
  - uid: "174094"
  - uid: "175310"
  - uid: "177406"
  - uid: "182120"
  - uid: "185242"
  - uid: "185247"
  - uid: "185252"
  - uid: "185272"
  - uid: "185275"
  - uid: "185289"
  - uid: "190692"
  - uid: "194359"
  - uid: "195263"
  - uid: "197482"
  - uid: "199478"
  - uid: "203405"
  - uid: "204509"
  - uid: "207199"
  - uid: "207218"
  - uid: "207221"
  - uid: "207388"
  - uid: "211513"
  - uid: "212955"
  - uid: "215350"
  - uid: "216171"
  - uid: "217172"
  - uid: "217174"
  - uid: "217279"
  - uid: "217953"
  - uid: "217954"
  - uid: "217961"
  - uid: "217977"
  - uid: "217994"
  - uid: "217997"
  - uid: "217999"
  - uid: "218001"
  - uid: "218004"
  - uid: "218024"
  - uid: "218090"
  - uid: "220776"
  - uid: "220786"
  - uid: "220857"
  - uid: "233851"
uid-files: "contribution/obsolete-see-dx11-pack-kinect2-nodes-files"
title: "[OBSOLETE, see DX11 Pack] Kinect2 Nodes"
image: "screenshot1385758883_0.png"
contribution: "true"
---

Pre node15 build, new features and some bug fixes, still badly lacks documentation, I know ;)

Latest update:
* Update to latest public sdk.
* Self contained, dependencies should all be there
* Support for some textures as raw (easier to use in compute shaders).
* Face and HdFace
* Experimental gesture support
* Experimental fusion support
* Some help patches (finally)
* Breaking change : Kinect skeleton tracking Id is now a string and not value anymore.

Disclaimer (from Microsoft):
“This is preliminary software and/or hardware and APIs are preliminary and subject to change.”

Same disclaimer for me, don't complain if a pin gets broken in a future release ;)

Note:
* Requires Windows 8 or Windows 8.1
* Requires DX11 pack 
* Only Works in 64 bits version

Install:
simply put the \kinect2 directory that is in the .zip in your \packs directory. 