---
uid: dfa6d979-0539-4765-bcd8-108cd8de1755
---

# addons change log 45beta33-01
released on 02 09 2014  

##  new nodes

* PolygonEditor (2d): create Polygons and edit them via Mouse and Keyboard interaction. Used in and initially developed for  <a href="https://vvvv.org/contribution/badmapper" class="extURL contribution" target="_blank">badmapper</a>.  

##  changed nodes
* Camera (Transform Orbit) now has "reset state" - controlled by input pins until any of its hotkeys are pressed, analogous to Camera (Transform Softimage)  
* Updated HTMLTexture node to use CEF 3.1750.1738 - see <a href="https://vvvv.org/blog/htmltexture-node-using-cef-3-now" class="extURL blog" target="_blank">htmltexture-node-using-cef-3-now</a>  
  * The node is now finally available in 64 bit.  
  * The node will spawn processes in background (like chrome does) which do the rendering, javascript etc.  
  * CEF can be configured through command line arguments to vvvv.exe - a general overview can be found here: http://peter.sh/experiments/chromium-command-line-switches/ - not all working though  
  * Changed default value of BaseUrl pin:  
  * New default is empty string in which case the node will use the local patch path as base URL.  
  * The node will also append a trailing slash to base URLs using the file:// scheme as described here: [/forum-alpha/64bit-htmltexture%28string%29-relative-local-paths-command-lines](https://vvvv.org/forum-alpha/64bit-htmltexture%28string%29-relative-local-paths-command-lines)  
  * The node is able to automatically set the size of its texture if width or height is set to zero.  
  * The node will hold on to previously computed values and the IsLoading output will stay true as long as  
  * CEF reports that it is loading content  
  * DOM was not retrieved yet  
  * Auto-size is enabled and document size wasn't retrieved yet  
  * A texture is in a dirty state  

##  fixed nodes
* Twirl (EX9.Texture Filter) was mistakenly spreaded inside, causing slowdown; fixed now  
* Mesh (EX9.Geometry Join Subset) now handles 32bit indexbuffers  
* HTMLTexture (EX9.Texture)  
  * <a href="https://discourse.vvvv.org/t/htmltexture-bug-(possibly-some-event-wrongly-handled)" class="extURL forum" target="_blank">htmltexture-bug-(possibly-some-event-wrongly-handled)</a> not crashing anymore.  
  * Fixed DOM issues with XML namespaces.