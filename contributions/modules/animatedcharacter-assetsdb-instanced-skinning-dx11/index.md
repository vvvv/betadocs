---
uid: "contribution/animatedcharacter-(assetsdb)-instanced-skinning-dx11"
uid-meta: "contribution/animatedcharacter-(assetsdb)-instanced-skinning-dx11-meta"
comments: 
 items: 
  - uid: "101783"
  - uid: "101846"
  - uid: "101864"
  - uid: "101865"
  - uid: "101869"
  - uid: "101872"
  - uid: "101875"
  - uid: "101916"
  - uid: "103690"
  - uid: "103720"
  - uid: "159863"
uid-files: "contribution/animatedcharacter-(assetsdb)-instanced-skinning-dx11-files"
title: "AnimatedCharacter (AssetsDB) Instanced Skinning DX11"
image: "AnimatedCharacter (AssetsDB) help-DirectX Renderer.png"
contribution: "true"
---

UPDATE

Latest version requires the DirectX11 pack.

This is Instanced Skinning in dx11 with thanks to microdee for the shader.

The module is still keeping track of all your assets if you asign it to a folder. This is nice for the workflow.

In this version I step away from any attempts to make it kinect-ready or provide a rigging or animation framework within vvvv.
This is only for animating multiple instance of one colladda file.

The Module was created before vux published fbx and better collada support in the assimp nodes, so basically it is outdated already.

However it can be useful if you want to have a definite workflow or if you want to reuse your old collada meshes, since it uses the old dx9 collada node.

Exporting Collada files in a way so it works with this module was hard to find out since many export chains do not work.

What workes 100% is:

Export from Cinema3d as FBX
Open in 3dsMax 2010 or 2011 and export again as .DAE (Open Collada)
The Open Collada Plugin can be found here https://github.com/KhronosGroup/OpenCOLLADA/wiki/OpenCOLLADA-Tools

This always workedd for us.

I have to point out that in the meantime the Assimp Nodes provide better functionality and I saw people using directly FBX or using .DAE files exported from native blender exporter. I point to microdees emeshes to see an example of this.



NOTE for the old dx9 versions that are extreamly outdated: You have to download the test models separately and extract the folder MODELS in the contribution folder.




