---
uid: 51cd18d8-5ff7-4002-bca8-335239dce89b
---

# change log - vvvv45beta33
released on 02 09 14  

## general
* always on top stays after toggling fullscreen: <a href="https://discourse.vvvv.org/t/always-on-top-command-not-honoured-after-going-fullscreen-and-back-with-a-window" class="extURL forum" target="_blank">always-on-top-command-not-honoured-after-going-fullscreen-and-back-with-a-window</a>  
* nodebrowser now works on "AlwaysOnTop" patches: <a href="https://discourse.vvvv.org/t/gui-bug" class="extURL forum" target="_blank">gui-bug</a>  
* fixed: <a href="https://discourse.vvvv.org/t/right-clicking-string-input-pins-containing-nil" class="extURL forum" target="_blank">right-clicking-string-input-pins-containing-nil</a>  
* fixed troubles with selecting links: <a href="https://discourse.vvvv.org/t/gui-strange-behaviour" class="extURL forum" target="_blank">gui-strange-behaviour</a>  
* fixed crash when bezier-handle of link was touched over a node  
* ctrl+g new windows pop up below cursor fixing: <a href="https://discourse.vvvv.org/t/ctl g-can-have-the-patch-window-behind-the-task-bar)) & [forum:gui-strange-behaviour" class="extURL forum" target="_blank">ctl g-can-have-the-patch-window-behind-the-task-bar](TODO INTERNALLINK:forum:gui-strange-behaviour" class="extURL forum" target="_blank">ctl g-can-have-the-patch-window-behind-the-task-bar) & ((forum:gui-strange-behaviour</a>  
* now use shift+click to open editor for gui-plugins: <a href="https://discourse.vvvv.org/t/ctrl- -click-non-consistent-behavior" class="extURL forum" target="_blank">ctrl- -click-non-consistent-behavior</a>  
* nodebrowser now keeps height as set and is always completely visible  
* optimized patch redrawing (should also reduce occurances of infamous IOBox bug)  
* a patch with evaluate=0:  
  * now now allows default patching/panning: <a href="https://discourse.vvvv.org/t/gui-strange-behaviour" class="extURL forum" target="_blank">gui-strange-behaviour</a>  
  * shows a "NO" cursor when hovering input pins indicating that you cannot change those  
* transformations: changed the way projection nodes and renderer work. default z visibility changed to 0..1 (was -1..1). see: <a href="https://discourse.vvvv.org/t/ortho-in-dx11" class="extURL forum" target="_blank">ortho-in-dx11</a> this was done to improve compatiblity with dx11 and custom shaders from other systems. if nothing is connected to the projection pin of a renderer though visibility is still -1..1 to reduce the effects of the change  
* got rid of freeze on connect: <a href="https://discourse.vvvv.org/t/extreme-cpu-usage-after-very-basic-io-nesting" class="extURL forum" target="_blank">extreme-cpu-usage-after-very-basic-io-nesting</a>  
* got rid of hidden connections by showing pin and connections always (pin visibility doesnt matter if connected) see: <a href="https://discourse.vvvv.org/t/hidden-pin-connections#comment-156594" class="extURL forum" target="_blank">hidden-pin-connections#comment-156594</a> (both problems/patches)  
* added a command to cleanup patches with corrupt links. see: <a href="https://discourse.vvvv.org/t/corrupt-link-inside-reader-(string)?full=1" class="extURL forum" target="_blank">corrupt-link-inside-reader-(string)?full=1</a>  
* fixed upstream value type / downstream reference type issue in plugin node connections introduced in beta32  
* SVG nodes now use native SvgDocument class: <a href="https://discourse.vvvv.org/t/svg-custom-struct" class="extURL forum" target="_blank">svg-custom-struct</a>  
* removed shortcut for UpdateView (ctrl+U)   
* scrolling of patches gets saved and boygrouped  
* introduced simple logging for setup.exe by calling it with /log  
* improved patch loading time a little  

## code editor
* for each file only one editor will be open  
* improved completion window for C# by adding async keyword and prioritizing entries by their kind (field/property etc.)  
* completion window for HLSL will only popup when pressing Ctrl + Space. It will also only show predefined functions and parameters as no proper AST for HLSL available.  
* fixed mouse wheel handling in code completion windows https://github.com/vvvv/vvvv-sdk/pull/203  
* fixed bracket search in code editor  
* removed runtime errors from editor  
* fixed exception when document ends with /*comment*/: <a href="https://discourse.vvvv.org/t/code-editor-bug" class="extURL forum" target="_blank">code-editor-bug</a>  

## new nodes
* Architecture (VVVV): <a href="https://discourse.vvvv.org/t/about-(vvvv)-x86x64-pin" class="extURL forum" target="_blank">about-(vvvv)-x86x64-pin</a>  
* MouseMatch (Mouse) node able to detect certain mouse events like up/down/wheel and click  
* SplitAt (Value/2d/3d/...) nodes - splits a spread at given position into two subspreads  
* AsDocument (SVG) and Join (SVG) make it possible to create and render multiple svg textures <a href="https://vvvv.org/blog/two-cool-svg-nodes" class="extURL blog" target="_blank">two-cool-svg-nodes</a>  
* ApplyTransform (Mouse) to transform mouse coordinates  
* Drag (Value) same as Drag (2d) only for one dimension  
* Merge (Mouse) - merges multiple mice to one  
* SecondLook (EX9 Softimage) - module that lets you debug your camera better than TestCamera did  
* ActiveWindow (Windows) returns the handle of the active window  
* added generic nodes (cons, queue, zip...) for: XElement, XDocument, XAttribute  

## fixed nodes
* Clean (String): <a href="https://discourse.vvvv.org/t/clean-(string)-leaves-dirt-when-trying-to-deal-with-only-spaces" class="extURL forum" target="_blank">clean-(string)-leaves-dirt-when-trying-to-deal-with-only-spaces</a>  
* Reader (Raw SharedMemory): <a href="https://discourse.vvvv.org/t/reader-(raw-sharedmemory)-name-not-updating" class="extURL forum" target="_blank">reader-(raw-sharedmemory)-name-not-updating</a>  
* Dir (File): <a href="https://discourse.vvvv.org/t/dir-file-count-in-subdirectories" class="extURL forum" target="_blank">dir-file-count-in-subdirectories</a>  
* IOBox (Enumeration): <a href="https://discourse.vvvv.org/t/show-slice-index-iobox-(enumerations)" class="extURL forum" target="_blank">show-slice-index-iobox-(enumerations)</a>  
* IOBox (Node): quick fix for "iobox node slicecount indicator wrong?!" [/forum-alpha/getslice-and-iobox-%28node%29](https://vvvv.org/forum-alpha/getslice-and-iobox-%28node%29)  
* RS232 (Devices) will reset outputs should an IOException occur: <a href="https://discourse.vvvv.org/t/rs232-connected-pin-does-not-works." class="extURL forum" target="_blank">rs232-connected-pin-does-not-works.</a>  
* = (Color) now spreadable <a href="https://discourse.vvvv.org/t/=-(color)-does-not-spread" class="extURL forum" target="_blank">=-(color)-does-not-spread</a>  
* Mouse should not get clamped to -1/1 anymore - <a href="https://discourse.vvvv.org/t/mousestates-node-clamps-positionxy-to-11" class="extURL forum" target="_blank">mousestates-node-clamps-positionxy-to-11</a>  
* cleanup on tcp (server & client) nodes evaluation and slice management. fixes a division by zero on startup  
* when disabling the Keyboard (Devices) nodes a keyboard device lost notification will be generated - downstream keyboard nodes will reset their internal state  
* fixed division by zero exception in collada loader  
* some outpins didn't evaluate their node when asked for their value - which could lead to strange phenomena. A thorough cleanup yielded a fix for the Expr.Error, OSCEncoder.Status, Renderer (HTML URL), Intersect.FormerIndex, Convert (String Legacy), Reader (Raw SharedMemory)  
* ConstantWrap (EX9.Effect) now works for spherical texturecoordinates  
* AsRaw (EX9.Texture) now ~30 times faster  
* DynamicTexture (EX9.Texture Raw) now ~10 times faster  
* Random (Value) now initializes correctly <a href="https://discourse.vvvv.org/t/random-not-really-random" class="extURL forum" target="_blank">random-not-really-random</a>  
* LFO (Value) does not bang twice on reset <a href="https://discourse.vvvv.org/t/resetting-lfo-while-cycles>0-causes-it-to-change-twice" class="extURL forum" target="_blank">resetting-lfo-while-cycles>0-causes-it-to-change-twice</a>  
* Intersect (Mesh Ray) is now also fast in dx9ex mode  
* Buffer nodes initialize corrcetly <a href="https://discourse.vvvv.org/t/buffer-(spreads)-strange-behavior" class="extURL forum" target="_blank">buffer-(spreads)-strange-behavior</a>  

## changed nodes
* Copier (File), Copier (File Async) now create target directory if it does not exist  
* IOBox (Value Advanced): <a href="https://discourse.vvvv.org/t/iobox-(value-advanced)-created-as-integer-default-max-and-min-why-so-low" class="extURL forum" target="_blank">iobox-(value-advanced)-created-as-integer-default-max-and-min-why-so-low</a>  
* IOBox (Value Advanced): <a href="https://discourse.vvvv.org/t/toggle-bug-(gui-only)" class="extURL forum" target="_blank">toggle-bug-(gui-only)</a>  
* Finder (VVVV) now has an option to search inside modules  
* Select nodes got tagged with resample, repeat, duplicate  
* global input device nodes will return dummy device in case no device is installed on the system: <a href="https://discourse.vvvv.org/t/error-without-hid-keyboard-(since-beta32- -32.1)" class="extURL forum" target="_blank">error-without-hid-keyboard-(since-beta32- -32.1)</a>  
* reworked MouseStates (Join) node so that new downstream observer will get notifications of current frame too: <a href="https://discourse.vvvv.org/t/new-mousestates-and-nil-%28beta32%29" class="extURL forum" target="_blank">new-mousestates-and-nil-%28beta32%29</a>  
* all file related nodes like Writer, Reader, Copier, ... now have a <span class="pin">Success</span>, <span class="pin">Error Message</span> and <span class="pin">Error</span> pin.  
* AsXElement (XML) now has a <span class="pin">Success</span> and an <span class="pin">Error Message</span> pin  
* Sync (Network) node now has a <span class="pin">Seek Threshold</span> and the port pin is spreadable to serve multiple clients on the same machine  
* Cursor (DX9) now has different "Cursor Types"  
* Player (EX9.Texture) will exclude hidden files: <a href="https://discourse.vvvv.org/t/feature-request-player-%28ex9.texture%29-option-to-exclude-hidden-files" class="extURL forum" target="_blank">feature-request-player-%28ex9.texture%29-option-to-exclude-hidden-files</a>  
* Reader (Raw SharedMemory) will not try to create a new shared memory location anymore. It will only try to open an existing one. Should that fail the new status pins will report about it and a warning will get written to the node's log.  

## plugininterface
* streams are now available as ulong/long https://github.com/vvvv/vvvv-sdk/pull/204  
* thorough delphi side error handling&logging of clr code throwing exceptions  
* VMath vecors and matrices now implement IEquatable<T> and IComparable<T> for your Linq pleasure  
* VColor got a simple Serialize/Deserialize method for RGBA color