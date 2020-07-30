---
uid: 0a6a5abe-656a-47ff-a88c-dce4d6a35f2e
---

# Change Log - vvvv33beta12
released on 20 12 06  

## general
* vvvv now can load a patch even when its extension is in capital letters  
* vvvv now no longer crashes when you have similarly named (apart from case) modules somewhere down in your /modules directory  
* boygrouping now copes with relatively referenced file-nodes (.fx, .dll)  
* EX9.Effects editor now should keep its focus for shortcuts  
* boxed windows finally stay in place when patch is scrolled (thanks for being patient)  
* added /logstartup commandline option which hopefully helps us tracking crashes that happen during startup  
* saver time handling  
* screenshots are now saved with timestamps  

## bug fixes
* Perlin (3d) evaluates its Z pin correctly  
* Queue (Texture) bugs resolved  
* XFile bug fixed  
* Renderer (Flash) now initializes correctly after being closed and being given a new filename  
* VideoIn (DShow9) fixed bug that made some devices (those using VideoInfoHeader2) crash rather than showing an image.  
* AsVideo (DShow9): graphs containing this node should cause less troubles now  
* IOBox (Value Advanced) no longer hangs vvvv when leftclicking while rightclick-changing value  
* DX9Texture (EX9.Texture) can now create mipmaps  
* Renderer (GDI), Renderer (Flash), Renderer (HTML String) and Renderer (HTML Url) now are in place when "inbox" mode while a patch is opened for the first time  
* Current Frame output of the MainLoop node is correct now  
* "Runtime Error 217" on startup related to odd midi drivers fixed  
* Torus (EX9.Geometry), Sphere (EX9.Geometry), Cylinder(EX9.Geometry) no longer crash when settig their resolution to 0  

## changed nodes
* DScaler (DShow9) can now be controlled via pins (used to be via property box)  
* Write (EX9.Texture) got an additional pin "Only Render on Save" that saves cpu while the node is not writing to disk.   
* ScopeSpread (DShow9) handles stereo signals now and is more stable  
* FFT (DShow9) handles stereo signals now and is more stable, new pin to enable/disable windowing  
* FileStream (DShow9) now also streams files from http:// and mms:// sources. no playlists yet.  
* VideoIn (DShow9) settings now default to systemsettings after loading. therefore they can be kinda saved.  
* both VideoTextureNodes got an output showing their input mediasubtype. revealing weather DXVA is used for decoding or not.  
* Mouse (System Window) now outputs the position of the mousewheel  

## new nodes
* OnResume (Windows) bangs when your computer resumes from hibernation or standby  
* Gregorian (Astronomy Join) encodes separate values to a date value  
* Switch (Color Input)  
* Switch (Color Output)  
* GetSpread (Color) for much faster selection of large consecutive spreads  
* GetSpread (Spreads) for much faster selection of large consecutive spreads  