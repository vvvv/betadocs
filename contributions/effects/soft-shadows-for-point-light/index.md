---
uid: "contribution/soft-shadows-for-point-light"
uid-meta: "contribution/soft-shadows-for-point-light-meta"
comments: 
 items: 
  - uid: "79209"
  - uid: "79210"
  - uid: "79234"
  - uid: "79247"
  - uid: "79251"
  - uid: "79278"
  - uid: "79334"
  - uid: "79340"
  - uid: "79404"
  - uid: "91843"
  - uid: "91856"
  - uid: "91892"
  - uid: "91902"
  - uid: "91904"
  - uid: "91905"
uid-files: "contribution/soft-shadows-for-point-light-files"
title: "Soft Shadows for Point Light"
image: "CmSS_0.png"
contribution: "true"
---

Soft shadows calculated from cubetexture depth so it works for point lights in every direction. It manages alpha channels too however <span class="node">AlphaTest (EX9.RenderState)</span> is required in that case. The softening technique is lame and simple as a rock so if anybody can do a better one please contribute it :P It's rendered separately so you just have to multiply the shadows on whatever scene you'd like to.