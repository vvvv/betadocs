---
uid: "contribution/interleaved-ssao-with-cubemap-lighting"
uid-meta: "contribution/interleaved-ssao-with-cubemap-lighting-meta"
comments: 
 items: 
  - uid: "51015"
  - uid: "51016"
  - uid: "52203"
  - uid: "52230"
  - uid: "52236"
  - uid: "52247"
  - uid: "52249"
  - uid: "52250"
  - uid: "52340"
  - uid: "52647"
  - uid: "52650"
  - uid: "52657"
  - uid: "52665"
  - uid: "52666"
  - uid: "52680"
  - uid: "52681"
  - uid: "52682"
uid-files: "contribution/interleaved-ssao-with-cubemap-lighting-files"
title: "interleaved SSAO with cubemap lighting"
image: "preview.png"
contribution: "true"
---

this is a vvvv adaption of ArKano22's updated SSAO technique. (a vvvv version of his original technique by joreg can be found [here](http://vvvv.org/contribution/ssao)) While the original version used 2d sampling, this one interleaves sampling in object space and therefore has the following benefits/changes:

- should be slightly faster
- view-independent sampling pattern - no more "boiling grain" during animation/camera movement


also ArKano22 added the following nice features to this version:

- texturing
- cubemap lighting
- self occlusion parameter to add more control over the general look

known problems:

-only edgeblur filter instead of hardware antialiasing

since this is my first contribution i'd appreciate any feedback on errors/optimisations concerning this effect.