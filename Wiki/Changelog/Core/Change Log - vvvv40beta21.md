---
uid: 402a2209-414a-4075-8f4b-420db0b15faa
---

# Change Log - vvvv40beta21
released on 15 04 09  

## general
* S+H & switches optimized for unused inputs. you now can better profile your patches.  
* tabbed patches no longer utilize CPU + further speed improvements in large setups with multiple tabbed patches  
* new commandline argument: /dontregister: probihibts registration of addflow, directshowfilter and .v4p filetype  
* freeframes finally work again without .net2 installed  
* resize windows proportionally by pressing CTRL while resizing one of its sides  
* Effects Transform Parameters can now deal with arrays + a little fix for initialized Value arrays (as e.g. with VertexNoise effect)  
* a disabled windowborder can now be saved (via parent-patch only!)  
* no more nasty desktop-reload-flash on vvvv startup  

## new nodes
* WithinView, WithinProjection, WithinNormaizedProjection, WithinViewport (Transform) for more or less camera and render independent 3d layers  
* Billboard (Transform) for 3d layers always facing the viewer   
* OneSided (Transform) e.g. for always readable text  
* Compare (String) a case-insensitive comparison between two supplied strings.  
* HID (Devices), HIDDecode (Devices) and HIDEncode (Devices) should make it possible to send/receive data from HID Devices.   
* eNet (Devices ecue Config) sets the Nic IP the ecue nodes should bind to   
* Verlet (Spreads Simple) calculates a simple verlet integration chain (translation of c# code originally written by <a href="http://vvvv.org/tiki-index.php?page=UserPagemilo" class="extURL" target="_blank">milo</a>)  
* Info (Enumerations) returns all Enums with Defaults and all their Entries.  

## fixed nodes
* Ping (Network) now deals with hostnames and ips   
* Select (MySQL) no longer has random dropouts when queried every frame  
* XPath (XML) should be faster in some cases, and it shouldn't loose memory anymore  
* VideoIn no longer BSODs with logitech qc pro 9000 (could also be relevant for other cams that had this problem)  
* Renderer (HTML URL) rewritten. no longer pops up javascript errors. now has an additional WindowHandle output useful if you need to send windowmessages (like mouseclicks) to the webbrowser.  
* Separate (String) no longer freezes with large spreadcounts  
* Expr (Value) evaluates expressions consisting of only one variable correctly now.  
* Changed flag is correctly propagated through io (node) nodes  

## changed nodes
* MidiController (Devices), MidiController (Devices Relative) and MidiNote (Devices) do not output all combinations of midi channel and controller number anymore.  
* Box, Cylinder, Grid, Sphere, Text & Torus (EX9.Geometry) mesh creator nodes are spreadable now  
* Tokenizer (String) now can deal with separators that consist of more than one character  
* Keyboard (System Global) has a new pin called Buffered Keyboard Output  
* Added 4th blend weight and 4 blend indices to VertexBuffer (EX9.Geometry Split).  
* Expr (Value) uses new expression parser from JEDI code library.  
  * (+) Much faster evaluation (about 10 times faster than old Expr node and about 40% faster than equivalent vvvv patch -> at least for tested expression 'sqrt(sqr(a)+sqr(b))').  
  * (-) Not as many operators available as before. Of course equivalent functions for missing operators were added.  
* GlyphInfo (String) has a new output: Position that returns relative positions for all characters in the given string  

## new modules
* Multiscreen (EX9) and MultiViewport (EX9)  
* Damper (Animation Jump)   
* Decompose (Transfom Vector)  
* NoSymTex (Transform)  
* TextureScale (Transform)  
* Grid (EX9 Test)   

## changed modules
* Sprite (DX9) now respects Aspect Ratio of Texture  
* fixed ScreenNumber (EX9)  

## plugins
* now support Enum in- and outputs and Mesh and Layer outputs  
* new Text (EX9) plugin  
* new ColladaFile (EX9.Geometry) + Mesh (EX9.Geometry Collada) plugins  