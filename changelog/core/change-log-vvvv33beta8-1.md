---
uid: 0542ef3a-627c-4801-ae49-a2e310384e4f
---

# Change Log - vvvv33beta8.1
released on 24 11 04  

## general
* c++/delphi developers: [write your own freeframe plugins](TODO INTERNALLINK:AddOns.FreeFrame) even with opencv features!  
* Alt+e now removes no longer existing externals  
* legacy modules no longer show up in nodelists  
* screenshot of the day will also generate a thumbnail for a faster homepage  
* no more restart needed when adding/removing USB/Firewire game- and videodevices  

## new nodes
* ScreenShot (Textures9) guess what!  
* LocalInfo (Windows) for now only outputs system language  
* Variance (Spectral) for statistics   
* HarmonicMean (Spectral) for statistics   
* RootMeanSquare (Spectral) for statistics   
* Indices (Spectral) illustrates how spectral nodes work with their slices  
* Trautner (FreeFrame DShow9) retrieves movement in specified areas of the image  
* Contour (FreeFrame DShow9) reads contours out of images  
* Port (Devices) access hardware ports (read/write). to use this node you must download the <a href="http://www.geekhideout.com/iodll.shtml" class="extURL" target="_blank">"io.dll"</a> and place it in your /bin or system32 directory. use with caution, can do anything to your hardware, including instant blue screens, hard disc corruption etc. we used it to access the printer port.  
* GameController (Devices JoyWarrior) for plug and play access to the JoyWarrior24A8-8 module  
* MidiOut (DShow9) renders a midi stream to the specified device  
* Mesh (Ex9.Geometry Join) creates a mesh dynamically receiving a vertexbuffer and an indexbuffer  
* VertexBuffer (Ex9.Geometry Join) takes position, specular + diffuse color, texturecoordinates etc. and creates a vertexbuffer out of it; to be used in conjunction with Mesh (Ex9.Geometry Join)  
* VertexBuffer (Ex9.Geometry Split) outputs the data in a vertex buffer; to be used in conjunction with GetVertexBuffer(Ex9.Geometry Mesh)  
* GetVertexBuffer (Ex9.Geometry Mesh) returns the vertexbuffer of a mesh  
* GetIndexBuffer (Ex9.Geometry Mesh) returns the indexbuffer of a mesh   
* CreateNode (VVVV) creates and replaces nodes by given id and parentpatch  
* DeleteNode (VVVV) deletes nodes by given id and parentpatch  
* Text (EX9.Geometry) creates a mesh containing 3D-Text. don't use this for dynamic text, cause it's quite expensive''  

## changed nodes
* FreeFramePlugins can be disabled (alternative to non possible switching)  
* FileStream (DShow9) now plays Quicktime and RealMedia files if you have installed <a href="http://home.hccnet.nl/h.edskes/mirror.htm" class="extURL" target="_blank">quicktime & real alternative</a>  
* FileStream (DShow9) got additional Midi Output  
* Window (Windows) reactivated Alpha Pin   
* Self (VVVV) addidtionally outputs patch caption  
* HWND, SendMessage, ShowWindow, Window now all work with numeric window handles  
* AVIParser (File) fixed posterframe-time bug  
* GeometricMean (Spectral) bugs fixed  
* bugs concerning all Spectral Nodes fixed (play with Indices (Spectral); try to use several bins..)  
* Pipet (EX9.Texture) now reports correct alpha  
* MidiShortOutput (Devices): fixed bug with multiple instances  
* Length (String), Change (String), Change (Value): got a fix with empty sets  