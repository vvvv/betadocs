---
uid: 61723d7d-f812-47a0-84bb-36e10d8b45c4
---

# change log - vvvv45beta34.2
released on 22 10 15  

## general 
* the Mouse (Devices Window Cyclic) module is replaced by a <span class="pin">Cycle On Mouse Down</span> on the Mouse (Devices Window) node  
* Camera (2d/Softimage/Orbit) are working again in fullscreen  
* removed broken link to dx9-websetup from setup.exe  
* fixed a rangecheck error that popped up in x64 builds when toggling a windows border  
* setup.exe is now shipping with its own version of websetup for dx9 since ms removed its downloadlink  

## changed nodes
* SubDir (File) now returns number of subdirs per input dir  
 
## fixed nodes
* ColladaFile/Mesh/Skeleton are now less picky with loading files  
* nodes in Skeleton category now throwing less errors  
* Separate (String) had newly indroduced troubles with certain intersperse characters <a href="https://discourse.vvvv.org/t/b34.1-separate-exception" class="extURL forum" target="_blank">b34.1-separate-exception</a>  
* Preloader (EX9.Texture) now reloads properly  
* Decompose (Transform Vector) now has a spreaded <span class="pin">Success</span> output  
* Reverse (Bin) nodes now update properly when changing the <span class="pin">Reverse</span> input  
* Find (String) had quite some spreading issues  
* Info (EX9.Texture) reports proper sharing-handle again in x86 versions <a href="https://discourse.vvvv.org/t/sharedtextureinfo-texture-handle-bug" class="extURL forum" target="_blank">sharedtextureinfo-texture-handle-bug</a>  
* DX9ToDX11 (EX9.Texture) now works also without any of the upstream renderers visible  