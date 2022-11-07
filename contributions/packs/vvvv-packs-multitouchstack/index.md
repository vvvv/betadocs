---
uid: "contribution/vvvv.packs.multitouchstack"
uid-meta: "contribution/vvvv.packs.multitouchstack-meta"
comments: 
 items: 
  - uid: "236491"
  - uid: "236691"
  - uid: "271067"
uid-files: "contribution/vvvv.packs.multitouchstack-files"
title: "VVVV.Packs.MultiTouchStack"
image: "Screenshot_1.png"
contribution: "true"
---

This is a rewrite of the MultiTouch Stack nodes mentioned here:
* https://discourse.vvvv.org/t/multitouch-stack/4924
* [multitouch-stack-revived](xref:contribution/multitouch-stack-revived)

The rewrite brings the following functions:

* Help patches
* Custom hit functions (e.g. image mask, transform, shapes)
* Custom hit events for any hit function (get an event callback when a custom area of a slide is hit, e.g. buttons on slides)
* Filter nodes
* Preview (DX11) for easy debugging
* TouchSimulator (thanks to xdnitro)
* Object Oriented everything

Since 2019-02-15

* Fallback Behaviours and Constraints (e.g. fall back to Translate if you rotate a Slide into a Constraint)
* DX9 help patches (thanks to Simon H!)

Thanks to Luma (xdnitro) for funding development.

The nodes are open source (https://github.com/elliotwoods/VVVV.Nodes.MultiTouchStack) and should run on AnyCPU.
