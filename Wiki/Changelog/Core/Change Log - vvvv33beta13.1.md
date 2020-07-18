---
uid: f1458564-62f5-4cb9-a968-bd7db4a54af8
---

# Change Log - vvvv33beta13.1
released on 04 07 07  

## general
* recompiled all .ax files in \bin (including freeframewrapper) to keep them bits fresh and improve filesize  
* probably fixed some of the nasty inspektor hickups  

## changed nodes
* Expr (Value): added output that reports errors. arguments-separator is now back to ,  
* Delaunay (2d): limited vertex count to 10.000 per triangulation; this allows to have more independant triangulations  
* GetPatch (VVVV): now can tell about selected nodes, use together with one of the many PatchAlias nodes to implement your own GUI features  

## fixed nodes
* FileTexture (EX9.Texture) works again with Pipet (EX9.Texture) and can load unlimited numbers of textures again  

## new nodes
* Scroll (Color)  
* Shift (Color)  
* PatchAlias (VVVV Name) : patch by name, use together with SetPatch  
* PatchAlias (VVVV ActivePatch) : activepatch, use together with SetPatch  