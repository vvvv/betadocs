---
uid: "contribution/dof"
uid-meta: "contribution/dof-meta"
comments: 
 items: 
  - uid: "50497"
  - uid: "50661"
  - uid: "50670"
  - uid: "53167"
  - uid: "53179"
  - uid: "53335"
  - uid: "53363"
  - uid: "53379"
  - uid: "53398"
  - uid: "53399"
  - uid: "53401"
  - uid: "60466"
  - uid: "62254"
  - uid: "62267"
  - uid: "62281"
  - uid: "62287"
  - uid: "62346"
uid-files: "contribution/dof-files"
title: "DOF"
image: "DOF Thumbnail.jpg"
contribution: "true"
---

New technique for Depth of Field. Works better on foreground objects.
more info: <http://http.developer.nvidia.com/GPUGems3/gpugems3_ch28.html>

 
##  Change log:
* DOF 2.0
Technique developped by Infinity Ward for *Call of Duty 4: Modern Warfare* that provides depth of field's key qualitative features in both the foreground and the background with minimal impact on total system performance or engine architecture. Requires Shader Model 2.0 hardware.

* DOF 1.1
new blur technique: gaussian blur (modified to blur correctly non square textures). better blur quality and also improved performances.

* DOF 1.0
Technique for rendering depth-of-field effects in realtime using image processing and compositing techniques with Poisson disc filtering. The use of a pre-blurred image in the post-processing step improves image quality by reducing aliasing artifacts. There are user friendly parameters for plane distance controls.