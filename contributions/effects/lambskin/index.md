---
uid: "contribution/lambskin"
uid-meta: "contribution/lambskin-meta"
comments: 
 items: 
  - uid: "235486"
  - uid: "235494"
  - uid: "235502"
  - uid: "235505"
uid-files: "contribution/lambskin-files"
title: "lambSkin"
image: "lambSkin Thumbnail.jpg"
contribution: "true"
---

A lambertian-like surface with light "bleed-through" -- appropriate for soft translucent materials like skin. The "subColor" represents the tinting acquired by light diffused below the surface.
Set the "rollOff" angle to the cosine of the angle used for additional lighting "wraparound" -- the diffuse effect propogates based on the angle of LightDirection versus SurfaceNormal.
Versions are provided for shading in pixel or vertex shaders, textured or untextured.