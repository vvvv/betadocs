---
uid: "contribution/splinesgpu"
uid-meta: "contribution/splinesgpu-meta"
comments: 
 items: 
  - uid: "70517"
  - uid: "70522"
  - uid: "70523"
  - uid: "70532"
  - uid: "70533"
  - uid: "70535"
  - uid: "70538"
  - uid: "70589"
  - uid: "70591"
  - uid: "70665"
  - uid: "71768"
  - uid: "86032"
  - uid: "86067"
  - uid: "102115"
  - uid: "102122"
  - uid: "102143"
uid-files: "contribution/splinesgpu-files"
title: "SplinesGPU"
image: "SplinesGPU.png"
contribution: "true"
---

given a set of 3d positions the shader interpolates to a higher resolution and calulates lines/curves/splines/ribbons with phong shading.


<div class="box">
**v.0.2**
* equal vs and ps version for ati cards
* fixed texture coordinates
* fixed thickness calculation for bezier
* spelling and some code beauty

**v.0.1**
* linear interpolation
* cosine interpolation
* cubic interpolation
* b-spline (third degree)
* tcb-spline (hermite interpolation with tension continuity and bias control
* bezier (cubic)
* piecewise bezier (cubic)</div>