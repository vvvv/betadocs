---
uid: "contribution/obsolete-setslice-(dx11.texturearray)-(dx11)"
uid-meta: "contribution/obsolete-setslice-(dx11.texturearray)-(dx11)-meta"
comments: 
 items: 
  - uid: "107985"
  - uid: "109715"
  - uid: "180029"
  - uid: "180095"
  - uid: "196976"
  - uid: "197186"
  - uid: "197188"
  - uid: "197232"
  - uid: "197240"
  - uid: "197293"
  - uid: "202550"
  - uid: "202556"
uid-files: "contribution/obsolete-setslice-(dx11.texturearray)-(dx11)-files"
title: "[OBSOLETE] SetSlice (DX11.TextureArray) (dx11)"
contribution: "true"
---

Simple plugin that allows you to store a texture into a Texture2DArray, that you can then retrieve in shader.

Different usages for it:
* RingBuffer
* Queue Texture
* Simple operations from previous frame
* Multi texturing with batched geometry
* Random morphing
* Custom animations

....

Source code included, so you can see how simple it is to write custom plugins for DX11 (without having to look at the big github codebase).

