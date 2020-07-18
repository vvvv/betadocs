---
uid: c694536d-bb31-4418-addd-909a577d121c
---

# addons change log 45beta32-01
released on 09 05 2014  

## changed nodes
* Typewriter (String) now has a <span class="pin">Max Length</span> input  
* Syslog (String) encodes syslog messages as raw  
* Logger (VVVV) logs a given string in the tty  
* ms-kinect nodes now use/return highres (640x480) textures  
* LD2000 (Devices) has its r'n'b color channels swapped to conform to the specification  
* SRTReader (File) uses default OS encoding  
* TodoMap (TodoMap) category dropdown is now editable, and some color fixes  

## new nodes
* RGB (Color Join/Split Vector)  
* 4d swizzle nodes  
* Levin (Spreads) is a spreadable addaption of the nativ Levin node  
* Combinations (Color / Enum / Raw / Spreads / String / Transform)  
* Variations (Color / Enum / Raw / Spreads / String / Transform)  
* Permutations (Spreads / String)  
* ApplyNearAndFar (Transform)  
* CameraPreview (Transform DX9)  

## fixed nodes
* fixed out of memory exception in HTMLTexture node using dx9ex by making use of two textures, one in default pool the other in systemmem pool - see <a href="https://discourse.vvvv.org/t/htmltexture-and-dx9ex-texture-sharing-breaks-directx-render-pipeline" class="extURL forum" target="_blank">htmltexture-and-dx9ex-texture-sharing-breaks-directx-render-pipeline</a>  
* DestroyBody (Bullet) was causing some red nodes for a frame.  
* TodoMap (TodoMap) : fix toggle for output routing.  
* FourRooms (Transform Viewport)  