---
uid: "contribution/volumetric-spot-light-(deferred)"
uid-meta: "contribution/volumetric-spot-light-(deferred)-meta"
comments: 
 items: 
  - uid: "269352"
  - uid: "269488"
uid-files: "contribution/volumetric-spot-light-(deferred)-files"
title: "Volumetric Spot Light (Deferred)"
image: "VolumetricLight.png"
contribution: "true"
---

This is a volumetric light implementation I was able to create mainly from this great resource:
http://www.alexandre-pestana.com/volumetric-lights/

The module also contains a bilateral upsampling shader which allows for blending of lower res and high res renderings, using the depth buffer and soby eliminating pixelated edges. Also a bilateral blur which is edge preserving.

Let it shine!