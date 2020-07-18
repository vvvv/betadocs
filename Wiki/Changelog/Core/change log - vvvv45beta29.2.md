---
uid: ea33d643-4801-48d0-a08a-7dd4d1b6cade
---

# change log - vvvv45beta29.2
released on 10 02 13  

## general
* fixed drawing of debug numbers  
* no more .xml files showing up in NodeBrowser  
* pluginwindows now report Mouse/Keyboard (Window)  
* cloning a node with NodeBrowser half outside desktop now allows scrolling to see all  
* opening Kommunikator once made beta29 instable and likely caused a crash  
* dynamic plugins  
  * fixed an issue when dynamic plugins turned red when opening the project explorer  
  * lib/nodes/plugins will also be added to the ReferencePath of a dynamic plugin project  
  * auto generated project files of dynamic plugins are now more similar to those of the addonpack (include x86 and x64 configuration)  
  * added Template (Raw)  
  * difff now supports "current" where the version is expected. That should help anybody who wants to rename own nodes and temporarily convert some patches. see help in the difffile. (in \lib)  

## new nodes
* AsRaw (EX9.Texture)  
* FrameDelay (Transform) as module  
* + (Raw) node with intersperse input (same as + (String)).  
* Cons (Raw)  

## fixed nodes
* Line (Ex9.Geometry) was broken in beta29x86  
* SpellValue 'Ascii' now behaves like pre-beta29  
* WindowLists (Windows) was broken in beta29  
* Rope (DX9) was broken in beta29x64  
* Midinodes were broken in beta29  
* Queue/FrameDelay (EX9.Texture) now return a sharedhandle in /dx9ex mode  
* Info (EX9.Texture) now reports sharedhandle in x64 builds  
* Leap (Devices) updated to Leapmotion SDK 0.7.3  
* Finder didn't work in release build  
* Fixed [exception](TODO INTERNALLINK:/forum-alpha/asvalue-%28raw%29-bug-with-byte) in AsValue (Raw)  
* Unzip (String Bin) returned empty spreads in some occasions  

## changed nodes
* OSCEncoder/Decoder now return/take the new Raw datatype  
* QRCode (EX9.Texture) reimplemented as a plugin based on http://qrcodenet.codeplex.com  
* RS232 (Devices) now features 2 more (higher) baudrates  
* Writer (String) module got 'Create Directory' pin back  
* HTMLTexture (EX9.Texture): Moved to CEF 1.1180.832  

## plugin interface
* IFlushable update  
  * Added "force" parameter to IFlushable.Flush method in order to circumvent certain changed flags and force a flush / write out to the pin.  
  * Added property "AutoFlush" to OutputAttribute which defaults to true in order to disable auto flush behaviour by plugin host. See the AsRaw/AsValue nodes for a use case.  
  * Improved performance of AsRaw (Value) and AsValue (Raw).  
* BufferedIOStream increases its size when writing values one by one. Very handy when length of stream is unknown.  

## modules
  * cleanup on multiscreen modules. deleted the dual view. made the spanmode legacy.  