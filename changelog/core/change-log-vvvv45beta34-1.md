---
uid: f49a9048-462a-4c7a-85cd-d75c1907ee57
---

# Change log - vvvv45beta34.1
released on 24 08 15  

## general 
* IOBoxes come with a hidden "Changed" pin. <a href="https://discourse.vvvv.org/t/changed-pin-on-ioboxes" class="extURL forum" target="_blank">changed-pin-on-ioboxes</a>  
* remote controlling: fix: <a href="https://discourse.vvvv.org/t/server-(vvvv)-exposed-iobox-string-behaviour" class="extURL forum" target="_blank">server-(vvvv)-exposed-iobox-string-behaviour</a>  
* fix for abstract node connections when routed over e.g. Switch (Node): <a href="https://discourse.vvvv.org/t/node-type-pins-connection-and-type-names-broken" class="extURL forum" target="_blank">node-type-pins-connection-and-type-names-broken</a>  
* if corrupt patch file can't be loaded -> red node (instead of missing node)  
* failable nodes like division node, mod node and several spectral nodes now get red on a division by zero. additionally you get a fast method of how to ignore those errors if this is what you want. the success pin gives you the opportunity to react otherwise on unsuccessful operations.  
* NAN, INF, MaxFloat (..) may be specified whereever you expect a number.   
* fixed a problem with unicode characters in xml-snippets: <a href="https://discourse.vvvv.org/t/(send)xml-inconsistency" class="extURL forum" target="_blank">(send)xml-inconsistency</a>  
* fixed a problem with node-label redrawing: <a href="https://discourse.vvvv.org/t/labelpin-vs-gui-redraw" class="extURL forum" target="_blank">labelpin-vs-gui-redraw</a>  

## fixed nodes
* AsValue. fix for bug introduced with beta34: <a href="https://discourse.vvvv.org/t/beta34-asvalue-behave-different" class="extURL forum" target="_blank">beta34-asvalue-behave-different</a>. also see NEW help patch  
* better support for infinity and NAN. Damper (Animation) shields against INF and NAN  
* fix for Node IOBox with BinSize = 0  
* Camera (2d Orbit Softimage) modules now also work on DX11 Preview windows  

## changed nodes
* WindowLists (Windows) now also returns handle for each window  

## new nodes
* ClippingEar (2d) - simple polygon triangulation  
* Cross (2d Bin) - cross with binsize  

## plugin interface
* SetComponentMode. 2 fixes that fix DX11 Renderer (not included ;)) fullscreen behavior. 