---
uid: "contribution/spatial-edge-blend-shader"
uid-meta: "contribution/spatial-edge-blend-shader-meta"
comments: 
 items: 
  - uid: "53354"
  - uid: "74870"
  - uid: "74873"
  - uid: "90467"
  - uid: "90545"
  - uid: "90643"
  - uid: "218483"
uid-files: "contribution/spatial-edge-blend-shader-files"
title: "Spatial Edge Blend shader"
image: "blendtest-DirectX Renderer_2010.09.25-17.55.38.jpg"
contribution: "true"
---

This shader enables you to edge blend in 3D, which is especially useful for projection mapping. This is a bit of a 'kitchen sink' shader which includes some other useful bits for mapping as well.

1.  Edge blending (aka Soft Edge) features
* Blend region size / position
* Blend direction unit vector input
* RGB gamma adjustment

1.  Other features
* Bicubic filtering
* Texture projection (for viewpoint matching)

1.  Requirements:
* Bicubic.fxh (needs to be in same dir as effect)
* BicubicFilterKernel.hdr


1.  To use
You need to edit the shader dependin on how many projectors you have.

Edit line #7 in the shader:
```
#define nRegions 3
```
and set nRegions to your number of projectors

##  Inputs
Set your blend vector to be the unit vector in the direction you want to blend in, e.g. if you're blending across the width of your sculpture, then chances are that you want the blend vector to be (1,0,0). This means that blends are cast across the x dimension.

Then set 'yBlends' (called 'Edge Blend Line' in the help patch) to the places where you want to blend.

Your renderer will need to have seperate viewports for each projector.
Check the help patch!

Also, if you want to project a texture onto the object using a projection matrix, then input your projection matrix into 'tProjection' as set 'useProjection' to 1.