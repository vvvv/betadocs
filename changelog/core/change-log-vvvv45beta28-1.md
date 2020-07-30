---
uid: 38457a3a-779e-4265-aec2-1be994c24aa9
---

# change log - vvvv45beta28.1
released on 27 08 2012  

## general
* middleclick on pins to pop-up nodes now works better with modules  
* fix <a href="https://discourse.vvvv.org/t/strange-bug-involving-framedelay-%28animation%29-and-scale-%28transform%29" class="extURL forum" target="_blank">strange-bug-involving-framedelay-%28animation%29-and-scale-%28transform%29</a>  
* fixed some modules where renderers weren't hidden  
* help patches for nodes with a special name (like +, -, *, ...) didn't come up in beta28  

## fixed nodes
* Text (EX9 Legacy) now works with /dx9ex  
* ColladaFile (EX9.Geometry) did not load the whole scene in beta28 (<a href="https://discourse.vvvv.org/t/collada-isssue)" class="extURL forum" target="_blank">collada-isssue)</a>  
* MouseState (Split) returns all pressed mouse buttons now  
* Filestream (DShow9 Boygroup) seek fixed  

## plugin interface
* plugins using ISpread<TextureResource> or ISpread<MeshResource> will not destroy their resources any longer when switching to fullscreen and the resources use the managed pool.