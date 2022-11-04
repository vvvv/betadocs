---
uid: "contribution/dx11-modules-and-shaders-addition-ii"
uid-meta: "contribution/dx11-modules-and-shaders-addition-ii-meta"
comments: 
 items: 
  - uid: "100225"
  - uid: "100230"
  - uid: "100289"
  - uid: "100300"
  - uid: "100306"
  - uid: "100309"
  - uid: "100331"
  - uid: "187803"
  - uid: "188284"
uid-files: "contribution/dx11-modules-and-shaders-addition-ii-files"
title: "DX11 Modules And Shaders Addition II"
image: "ParticleShere.png"
contribution: "true"
---

A few  more addons in DX11 flavour.

Modules

GeometrySplit (gsfx)
//Kind of MeshSplit using gsfx buffer and StreamOut
TesselatorGeometryTypes (gsfx) 
//Tesselate Input Geometry and Output via buffers.
GeometrySplitStructured (CS) 
//MeshSplit using gsfx buffer and StreamOut also shows how to read from buffer and compute shader.

OBJ Exporter (Mesh) 
//Export Geometry in OBJ format. 
http://en.wikipedia.org/wiki/Wavefront_.obj_file

MultiScreen (DX11)
Projector (DX11)
Cursor (DX11)
Axis (DX11)
Arrow (DX11)
Quad (DX11)

SystemAssets (File)
SystemTexture (DX11.2d)

Effects:

Nvidia 

Some porting from Nvidia sites.
http://developer.download.nvidia.com/shaderlibrary/webpages/shader_library.html
http://developer.download.nvidia.com/SDK/10.5/direct3d/samples.html

AnisotropicHilight
balloon
blinn
blinn_bump_reflect
carpaint_texColor
glossyWetHilight
gooch_bump_reflect
Grisaille
lambert
lambSkin
metalP
plasticD
subcutaneous
Toksvig_NormalMaps
SolidWireframe


Other:

3DVisionTypes (DX11)

Generate 3D Stereoscopy contents using diferent techniques: 

-Side By Side Horizontal and vertical 
Very common in Samsung Tv,s.

-Interlace most common in 3D projectors.
Credtis to: mediadog & microdee 
[passive-(interlaced)-3d-shader](https://discourse.vvvv.org/t/passive-(interlaced)-3d-shader)
(This one i could not test with glasses but should work or be close to).

-Anaglyph
Credtis to :woei
[anaglyph-patch](https://discourse.vvvv.org/t/anaglyph-patch)

Patches:

-Oscillator (DX11)
Shows how to get similar filter to Oscillator node via Compute Shader.
Credtis to :Gregsn
[damper-equations](https://discourse.vvvv.org/t/damper-equations)
<span class="node">oscillator (animation advanced)</span>


-Decay (DX11)
Shows how to get similar filter to Decay node but IIR style via Compute Shader.

-ParticleShere 
Playing with some particles for Fun ;D 