---
uid: "contribution/shadertoys"
uid-meta: "contribution/shadertoys-meta"
comments: 
 items: 
  - uid: "155973"
  - uid: "156003"
  - uid: "156012"
  - uid: "156020"
  - uid: "156021"
  - uid: "156084"
  - uid: "156095"
  - uid: "156100"
  - uid: "156102"
  - uid: "156122"
  - uid: "156208"
  - uid: "156219"
  - uid: "156236"
  - uid: "156275"
  - uid: "156573"
  - uid: "157210"
  - uid: "157265"
  - uid: "157334"
  - uid: "157658"
  - uid: "157659"
  - uid: "157689"
  - uid: "203782"
  - uid: "217178"
  - uid: "218157"
  - uid: "218200"
  - uid: "218204"
  - uid: "218927"
  - uid: "218938"
  - uid: "228852"
uid-files: "contribution/shadertoys-files"
title: "shadertoys"
image: "shadertoys04.jpg"
contribution: "true"
---

ported some shaders from https://www.shadertoy.com/ ...

feel free to optimize and update this contribution.

issues:
* they'd better be written as .tfx
* procedural noise is taking muuuch gpu - didn't get lut-versions to work
* some glsl-leftovers
* i'm sure there are more optimizations by using hlsl/dx11 advantages


/sebl

0.4 Added a ray marched primitives and a substitute(string) for converting the GLSL, look out for matrices that haven't been fully initiated (overloaded, I think is the term) 
