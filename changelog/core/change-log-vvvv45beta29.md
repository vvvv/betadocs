---
uid: 62f3cffa-5595-4b84-8f9d-6943a828c24c
---

# change log - vvvv45beta29
released on 24 12 12  

## general
* vvvv now comes in a 32bit and a 64bit flavour, the second of which has some nodes missing, see: <a href="https://vvvv.org/blog/vvvv-64bit" class="extURL blog" target="_blank">vvvv-64bit</a>  
* vvvv is now fully unicode internally which removes taking care of ANSI/UTF8 settings on various string-handling nodes, see: <a href="https://vvvv.org/blog/unicorn-in-alpha-builds" class="extURL blog" target="_blank">unicorn-in-alpha-builds</a>  
* there is a new basic data-type RAW for low-level bytehandling, see: <a href="https://vvvv.org/blog/new-datatype-raw" class="extURL blog" target="_blank">new-datatype-raw</a>  
* necessary switch to AddFlow5 component for gui slows down moving of many nodes (sorry for that)  
* fix for a special case of refactoring/grouping  
* CreatePatchInPatch now creates window and node at cursor  
* now using a new Directory-Selection Dialog  
* crack now checks for availability of MSVC++ 2008 redistributables as well  
* added /unregister commandline-option for crack.exe  
* some boygroup fixes:  
  * Values are now transmitted as double (LittleEndian). was single (BigEndian). more bandwidth but less cpu usage  
  * Strings are transmitted with UTF8  
  * Colors are transmitted as colors (much faster)  
  * The new raw datatype can be sent over network (boygroup)  
  * IOBox (String) read from wrong array (action array) in case it was boygrouped  
* fixed initialization issue when creating plugin pins [(/forum-alpha/weird-new-behavior)](TODO INTERNALLINK:(/forum-alpha/weird-new-behavior))  
* Fixed random memory corruption  
* Fixed some XML error warnings on startup  
* If creation of plugin fails, error won't be logged every frame anymore  

## new nodes
* Leap (Devices) implements  the leap motion device SDK  
* Player (EX9.Texture) - a high-performance player for picture sequences  
* HTMLTexture (EX9.Texture) - a chromium based texture for playing back youtube, flash and more see: <a href="https://vvvv.org/blog/htmltexture-(ex9.texture)" class="extURL blog" target="_blank">htmltexture-(ex9.texture)</a>  
* a series of new XML-handling nodes: <a href="https://vvvv.org/blog/xml-nodes-added-to-alpha-builds" class="extURL blog" target="_blank">xml-nodes-added-to-alpha-builds</a>  
* Reader (RAW), Writer (RAW) for reading binary files  
* PinInfo (VVVV)  
* Path (SVG) lets you build advanced 2d graphics paths   
* Database (MySQL Network) nodes  

## removed nodes
* all Database (MySQL) nodes. Please use the new MySQL database nodes from the addonpack.  
* PictureStack (EX9.Texture*) is now legacy. See new Player (Ex9.Texture) node.  
* Replaced Vector (Spreads Join/Split) with Zip/Unzip (Value)  

## changed nodes
* Reader/Writer (File) are now Reader/Writer (String) modules that default to UTF8 encoding  
* LogFile (VVVV) got a <span class="pin">ShowTimeStamp</span>  
* UDP (Network Server/Client) now have RAW in/outs  
* original UDP (Network Server/Client) are now UDP (Network Server/Client String) modules  
* TCP (Network Server/Client) now have RAW in/outs  
* original TCP (Network Server/Client) are now TCP (Network Server/Client String) modules  
* RS232 (Devices) now has RAW in/outs  
* original RS232 (Devices) is now RS232 (Devices String)  
* all nodes of the category MySQL had to be replaced by plugins  
* OSCEncoder/Decoder (Network) now have RAW in/outs  
* GUI 2d nodes work with the new mouse state and can handle multitouch  
* Added "Allow Empty Spreads" option to Zip node  

## fixed nodes
* Cursor (System) now has its Y input flipped  
* DX9Texture (EX9.Texture) in cubemap mode now works with multiple rendertargets  
* PatchState (VVVV) got a memleak fixed  
* HTTP (Network Get/Post) now copes with https connections  
* fixed a special case of Linearspread: <a href="https://discourse.vvvv.org/t/faulty-results-for-spreaded-linearspread" class="extURL forum" target="_blank">faulty-results-for-spreaded-linearspread</a>  
* CreateEnum bug fix  
* Added support for multiple texture coordinates to collada loader.  

## plugininterface
* IPin2.Subtype now includes enumName for enumpins  
* ColorPin now also returns priority  
* Updated to SlimDX version 4.0.13.43  
* The "Texture Out" pin of plugins using the texture template class will always be the left most pin  
* Fixed COM exception when setting SubType on INodeIn/INodeOut  
* Added possibility to set Dimension in IOAttribute for IO objects which do not have an inner generic data type set (like the pointer types)