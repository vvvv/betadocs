---
uid: "contribution/texture-avi-writer-(dx11)"
uid-meta: "contribution/texture-avi-writer-(dx11)-meta"
comments: 
 items: 
  - uid: "179858"
  - uid: "179859"
  - uid: "179862"
  - uid: "179987"
  - uid: "180025"
  - uid: "180320"
  - uid: "181807"
  - uid: "183166"
  - uid: "186365"
  - uid: "189720"
  - uid: "195144"
  - uid: "204894"
  - uid: "211859"
  - uid: "232279"
  - uid: "240830"
  - uid: "240837"
  - uid: "248669"
  - uid: "248822"
  - uid: "272029"
  - uid: "273161"
  - uid: "273163"
  - uid: "273186"
  - uid: "273189"
uid-files: "contribution/texture-avi-writer-(dx11)-files"
title: "Texture AVI Writer (DX11)"
image: "icon_10.png"
contribution: "true"
---

Record texture in avi file using H.264 codec (FFmpeg 2.8.1) with fast speed.

###  Some restrictions
* Support only R8G8B8A8_Unorm format and multiples of two texture sizes
* Not spreadable

###  Update
**v1.2**
* Fix floating framerate,
* Fix memory leak,
* Update dependencies

Submit bugs and requests to:
https://github.com/gumilastik/VVVV.TextureWriter
