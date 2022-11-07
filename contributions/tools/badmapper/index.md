---
uid: "contribution/badmapper"
uid-meta: "contribution/badmapper-meta"
comments: 
 items: 
  - uid: "110194"
  - uid: "110231"
  - uid: "154421"
  - uid: "154422"
  - uid: "154424"
  - uid: "154488"
  - uid: "155721"
  - uid: "165404"
  - uid: "165411"
  - uid: "165412"
  - uid: "168070"
  - uid: "173024"
  - uid: "183729"
  - uid: "183740"
  - uid: "183744"
  - uid: "183756"
  - uid: "183757"
  - uid: "219783"
  - uid: "219794"
  - uid: "219812"
  - uid: "219824"
  - uid: "234747"
  - uid: "234753"
  - uid: "240817"
  - uid: "240827"
  - uid: "240852"
  - uid: "240853"
  - uid: "250372"
  - uid: "250716"
  - uid: "266644"
  - uid: "267756"
  - uid: "270138"
  - uid: "274751"
  - uid: "274753"
  - uid: "274765"
  - uid: "274766"
  - uid: "274767"
  - uid: "274768"
  - uid: "274849"
  - uid: "277552"
  - uid: "279141"
  - uid: "280223"
  - uid: "280227"
  - uid: "280268"
  - uid: "280282"
uid-files: "contribution/badmapper-files"
title: "badMapper"
image: "badMapperV3.jpg"
contribution: "true"
---

Inspired by [MadMapper](http://www.madmapper.com/) and [mapping-toolkit (alpha](xref:contribution/mapping-toolkit-%28alpha%29)) badMapper allows to select multiple rectangles from a SourceRenderer and distort those (via homography) in a DestinationRenderer.

Provide a texture with your own content, point your projector to the surfaces you want to be mapped and go fullscreen on it with the *Destination* Renderer. Create/place/size selections in the *Source* and then drag their corresponding cornerpoints to their targetposition by directly operating in the *Destination Preview* Renderer. Selections can be tweaked pixelprecise via keyboard, vertices snap, mappings can be saved/loaded, ... which makes this a perfectly usable tool for simple scenarios. 

Built in an ultra-modular fashion that allows it to be easily adapted to a DX11 version.

Also available via [github](https://github.com/vvvv/badMapper).