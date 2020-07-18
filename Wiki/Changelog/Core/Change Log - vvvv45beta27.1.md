---
uid: 4137c0b1-1896-4ec6-ad32-2a42043b5c04
---

# Change Log - vvvv45beta27.1
released on 20 02 12   

## general
* no longer needs .net3.5SP1 installed to run, .net4 is enough  
* no more troubles with "missing" nodes with plugins actually present  
* if exception dialog is visible mainloop of vvvv will be stopped  

## fixed nodes
* CreateNode and GetPatch failed in b27  
* MonitorPower (System) works again  
* VideoIn (DShow9) got a problem fixed with switching between 2 drivers  
* FileStream2 (DShow9) failed to run on some systems  
* Finally (VVVV) now works as advertised  
* Random (Value) in integermode didn't equally distribute random values  
* Undistort (DShow9 OpenCV) got its Rows/Columns inputs fixed   
* Substitute (Spreads) was broken if patch contained a Sift (Value) node  
* Database (MySQL Network) works again  
* Mesh (EX9.Geometry Join) and VertexBuffer (EX9.Geometry Join) now dont evaluate upstream graphs when apply = false and therefore are very fast in those cases. S+H and Switch tricks not needed anylonger.  
* LinearFilter (Animation): fixed a bug: <a href="https://discourse.vvvv.org/t/spread->-linearfilter-does-not-filter-linearly" class="extURL forum" target="_blank">spread->-linearfilter-does-not-filter-linearly</a>  
* Renderer (Flash): fixed bug: <a href="https://discourse.vvvv.org/t/which-flash-player-version" class="extURL forum" target="_blank">which-flash-player-version</a>  
* Automata (Logic): fixed bug: <a href="https://discourse.vvvv.org/t/automata-state-pin-problem" class="extURL forum" target="_blank">automata-state-pin-problem</a>  
* Quad (SVG): fixed corner radius bug: <a href="https://discourse.vvvv.org/t/renderer-%28svg%29-quad-%28svg%29-corner-radius" class="extURL forum" target="_blank">renderer-%28svg%29-quad-%28svg%29-corner-radius</a>  
 
## changed nodes
* added <span class="pin">Scratching</span> output to Timeliner that reports when the timebar is being draged  
* VideoTexture (EX9.Texture): added an adapter pin, that allows you to specify on which adapter the texture should run.  

## new nodes
* DeleteSlice, deletes slices of a spread at the given index  

## plugininterface
* direct3d9 interface change: <a href="https://vvvv.org/blog/direct3d9-plugin-interface-change" class="extURL blog" target="_blank">direct3d9-plugin-interface-change</a>  
* new interface IStartable, which can be used to run some initialization code when vvvv starts up / shuts down or plugin assembly gets loaded  
* ISpread<Quaternion> and ISpread<Color4> from SlimDX can now be imported by a plugin  
* in some circumstance IPluginDXResource.UpdateResource was called multiple times per device. this happended for example if a Renderer and an Info node were connected downstream.