---
uid: 492c01dc-8a5c-4e31-9b02-10a3f369baa5
---

# Change Log - vvvv45beta26
released on 17 08 11  
## general
* more control over and comfort for numeric values and strings   
  * you still can trust on the magic mechanism that helps you with entering valid values into ioboxes (subtype inference). Valid are only values that nodes connected to the output of the iobox can works with... (Think of the <span class="pin">Index</span> (subtype: integer) of a <span class="node">GetSlice (Spreads)</span> connected to an iobox resulting in an iobox that helps you with entering integer values...)  
  * however from now on you additionally can modify this *subtype* (and therefore behavior of an input pin of e.g. a module and its upwards connected ioboxes) in the following way:  
  * <span class="node">IOBox (String)</span> now let's you   
  * set the <span class="pin">Content Type</span> (Any, SingleLine, FileName, Directory, URL, IP) reflected by a small (grey) icon,  
  * a <span class="pin">Default</span> string (for when the user resets the pin)   
  * a <span class="pin">File Mask</span> (for when you choose "FileName" as the content type (check the help patch for an example that only let's the user choose files of a certain file type)   
  * and a <span class="pin">Maximum Characters</span> that restricts the user to only enter some few characters.  
  * <span class="node">IOBox (Value Advanced)</span> now lets you   
  * set the <span class="pin">BaseSubType</span> (Real, Integer, Boolean) (meaningless configuration pins as a reaction get hidden)  
  * specify the (visual) <span class="pin">Precision</span> of a real number  
  * enter a <span class="pin">Vector Size</span> used for visual grouping of slices and as a default slice count when user resets via Alt-Right-Click  
  * again a <span class="pin">Default</span> value   
  * the <span class="pin">Units</span> of measurement to get a better feel for certain values (use **s** for seconds,**m** for meters...). (these can easily be entered directly in the iobox when entering a value, e.g. "5 km/h")  
  * <span class="pin">Minimum</span> and <span class="pin">Maximum</span> now also modify the subtype, that helps entering valid values in this and all upwards connected ioboxes.   
  * if the string representation of a value wouldn't fit into the iobox, a shorter is found by cutting of least significant digits.  
  * "Integer" added to the quick node list  
  * tooltips for vector & matrix subtypes also show up on ioboxes  
  * general improved accuracy in tooltips (scientific notation is used for very big and very small values, otherwise the shortest easiest representation is used). A ~ says that the decimal representation of the value would be longer and has been cut off.  
  * still ioboxes created over middle-click on any vector pin followed by a middle-click on the patch are the easiest way to configure ioboxes  
  * now most subtype properties are copied into the iobox settings and typically need no further adjustment. (e.g. try this feature by fully configuring a first iobox, then middle-clicking on its in or output pin, followed by a middle-click on the patch)  
  * hint: a further middle click labels the iobox (no new feature)  
  * no longer sets the "ColsRowsPages" SliceCount mode, which eases the use of vector ioboxes as inlets for modules  
  * better defaults for vectors, filenames and paths  
  * **relative paths** (to files and folders) are now converted into absolute paths relative to the patch where they were entered. they still are saved as relative paths though. this should solve bugs in modules that received file paths, since they now already receive a solid absolute path...  
  * <span class="pin">Pin Visibility</span> lets you specify how an iobox shows up as a pin from outside the patch (if a <span class="pin">Descriptive Name</span> has been entered))  
* less confusing node pin tool tips  
* better root  
* major fixes on texture feedback and resource handling for multi monitor setups  
* new quitoptions: open patch, new patch, quit  
* implemented new caching mechanism via nodelist.xml;   
  * if a search path (added via <span class="node">NodeList (VVVV)</span>) contains a nodelist.xml, all node infos beneath this path are read from the nodelist.xml file only.  
  * if a search path does not contain a nodelist.xml, the directory is scanned as usual.  
  * vvvv and the addonpack are shipped with their nodelist.xml files respectively.  
  * for power users: a nodelist.xml file can be generated for a user defined search path by calling 'vvvv.exe /nodelist SEARCH_PATH'.  
  * comparison of startup times incl. addonpack (after windows reboot / second time):  
  * beta23 (1047 nodes): ~9s / ~3s  
  * beta26 (1380 nodes): ~12s / ~3s  
* <span class="pin">Layer</span> outputs on Quads, Effects (...) only show up one slice, reflecting that you can't index into a "layer spread".  
* some filter nodes now work with "seconds" (time value subtype)  
* Reloading a patch now doesn't result in disconnecting from its surroundings in the parent patch any longer. You are also asked for if you would want to save your work from now on.   
* fixed some (last) enum bugs  
* under some circumstances disabled nodes using transform input pins didn't fetch upstream transforms when switched to enabled state  
* a color pin didn't report that its values changed if the change wasn't greater than a certain threshold. this led to various inaccuracies in some nodes.  
* unfounded red nodes bug fix  
* catweasels conversion bug fixed. <a href="https://discourse.vvvv.org/t/addons-path-incorrect-on-start-patch-before-vvvv.exe" class="extURL forum" target="_blank">addons-path-incorrect-on-start-patch-before-vvvv.exe</a>  
* bug fix: nodelist is evaluated before any other nodes are evaluated. therefore dummynodes are replaced in time before they are evaluated.  
* fixed some convvverter bugs, which should reduce corrupted patches  
* crack.exe does better checks for existing components and offers more explanations  
* fixed mouse freeze/crash for cases when no Mouse (System Global) is used  
* freeframe and vst .dlls can be referenced locally again  
* no more problems with patches not loading that store "invalid characters"  
* new effects compiler that is substantially faster in special cases and no longer allows the ps_1.0 profile  
* saving *.fxh files shouldn't lead to multiple recompilations of effects.  
* some bug fixes regarding replacement of missing (red) nodes.  
* fixed an issue where a change from an output pin of type 'Node' wasn't acknowledged by downstream nodes which were evaluated some frame later.  
* Interlave plugins from <span class="user"><a href="https://vvvv.org/users/vux" class="extURL" target="_blank">vux</a></span> are in the difff.xml and convert to <span class="node">Vector (Spreads Join)</span> now.  
* patches that where edited once in versions >= beta25, than again in versions < beta25 could get corrupted when opening with current vvvversions again. fixed that weirdo <a href="https://vvvv.org/contribution/SiftNearmost (2d" class="extURL contribution" target="_blank">SiftNearmost (2d</a>)  
* better error reporting can be activated via the main menu (ExceptionDialog) or enabled via command line argument '/showexceptions'.  
* dynamic plugin templates reference System.Core, SlimDX and VVVV.Utils3rdParty by default now  
* better error reporting if dragging a dynamic plugin on a patch (*.csproj file) fails  
* dynamic plugins couldn't resolve referenced assemblies in some cases  

## GUI
* Renderers can now be docked again  
* fixed heavy lag when changing values on iobox or pin  
* fixed problem with IOBox (Color) when leftclicking while rightdragging  
* fixed problem with deleting nodes while in locked-patch-mode  
* fixed a few out of range exceptions for NodeBrowser: <a href="https://discourse.vvvv.org/t/.node-browser-bug" class="extURL forum" target="_blank">.node-browser-bug</a>  
* CodeEditor no longer zooms back to 0 on AltGr+0  
* @ works again on danish keyboards  
* alt+e on patch now opens explorer with current patch focused (moved rescanning for freeframes and vsts to alt+shift+e)  
* introduced icons for subtypes in string ioboxes  
* fixed: clicks on enumpulldowns in inspektor sometimes set mousecursor to topleft  
* new drawing style for bangs  
* windowswitcher is now bigger by default  
* fixed problems with scrolling values/colors on multimonitor setups  
* disable fx-autocompletion by removing \bin\hlsl.fnr  
* fixed index out of range exception when playing with node and window selection  
* only one instance of a patch can now be opened via doubleclicking on a .v4p in explorer  
* Shift+Alt+F4 to force quit (no questions asked)  
* fixed out of range exceptions in project explorer, if one tried to sort assemblies in the reference dialog  
* press ctrl+f in reference dialog of project explorer to search in global assembly cache  


## changed nodes
* s/r nodes: more than one sender can send values on a certain channel. receivers connect to the nearest in terms of the patch hierarchy  
* <span class="node">Finder (VVVV)</span> now uses  '<' to search globally, '>' to search inside of current patch and sub-patches  
* <span class="node">SetPatch (VVVV)</span> has new input: <span class="pin">Add to UNDO History</span>  
* <span class="node">Info (EX9.Texture)</span> has new enum output: <span class="pin">Format</span>  
* <span class="node">DX9Texture (EX9.Texture)</span> can now render to cubemap  
* <span class="node">TextMetrics (String)</span> is now spreadable  
* <span class="node">Intersect (3d Quad Line)</span>, <span class="node">Intersect (3d Mesh Ray)</span> and <span class="node">Intersect (3d Mesh Subset Ray)</span> are moved to legacy. there is now <span class="node">Intersect (EX9.Geometry Quad)</span> and <span class="node">Intersect (EX9.Geometry Mesh)</span> instead. the default line is in z direction, so no rotate for mouse intersects necessary any more.  
* Queue nodes <span class="pin">do Insert</span> is now called <span class="pin">Insert</span>, <span class="pin">Reset</span> added, entering a negative frame count means infinite size  
* <span class="node">LFO (Animation)</span> got a <span class="pin">Change</span> output pin  
* VideoTexture nodes now default to NonPow2 texture  
* all IOBoxes have their SliceOffsets now hidden to Inspektor, value IOBox also hides X pin by default  
* Constant_2.0.fx and Constant.fx are merged to Constant.fx  
* <span class="node">Differential (Spreads)</span> has new <span class="pin">Bin Size</span>  
* <span class="node">TypoSpread (Spreads)</span> got a <span class="pin">BinSize</span> ouput that says how many points are in each character.  
* Buffer (EX9.Texture) has now spreadable [Pin:Index](TODO INTERNALLINK:Pin:Index)  

## fixed nodes
* <span class="node">Triangle (DX9 Indexed)</span> now has color pins/modes working  
* <span class="node">Mesh (EX9.Geometry Join)</span> faster in cases of high indexcounts  
* <span class="node">TypoSpread (Spreads)</span> now works with unicode characters  
* <span class="node">Pipet (EX9.Texture)</span> can now read floating point textures and is faster in many cases  
* DynamicTexture (Value/Color) now have their Width/Height spreadable correctly  
* <span class="node">DetectObject (FreeFrame DShow9)</span> works again  
* createEnum bug fix  
* <span class="node">String2Enum (Enumerations)</span> : no red node on startup  
* SetSlice () nodes bug fix  
* <span class="node">Queue (EX9.Texture)</span> bug fix  
* <span class="node">Finder (VVVV)</span> fixed drawing issues of links between s and r nodes and does no longer redraw whole graph if scope is global and active window changed  
* <span class="node">Find (String)</span> fixed problem for mode 'All' when filter was not found  
* <span class="node">Text (EX9)</span>: more options, spreadable size, font etc., brush and text alignment bugs in multiline modes fixed  
* <span class="node">Sift (String)</span> fixed wrong index in 'case sensitive' mode and hit count bug for multiple occurrences in words  
* all DX9 nodes now like <span class="node">Grid (DX9)</span> now work with 32bit indexbuffers enabling higher spreadcounts in combination with high resolution grids...  
* <span class="node">QuickNodes (VVVV)</span> working again  
* for Mesh-Sink nodes fixed troubles with nil on input  
* <span class="node">Integral (Spreads)</span> should handle two dimensional spreads properly now  
## new nodes
* RingBuffer nodes for all types  
* Buffer nodes for all types  
* <span class="node">Polar (3d Vector)</span>  
* <span class="node">Cartesian (3d Vector)</span>  
* <span class="node">Polar (2d)</span>  
* <span class="node">Cartesian (2d)</span>  
* <span class="node">Polar (2d Vector)</span>  
* <span class="node">Cartesian (2d Vector)</span>  
* <span class="node">Decompose (Transform Vector)</span>  
* <span class="node">RelativePath (File)</span>  
* <span class="node">AbsolutePath (File)</span>  
## plugininterface
* added non-generic version of ISpread and IDiffSpread  
* use default logger with attached plugin logger as ILogger implementation for plugins to ensure calls are marshaled to the GUI thread when called from other threads.  
* changed signatures of methods IAddonFactory.ExtractNodeInfos  
* ISpread<ISpread<...>> implementations weren't properly disposed.  
* added new property Timestamp to INodeInfoFactory  
* INode2 didn't emit Renamed event after node info changed.  
* bug fix that makes the Cons<T> node work for user structs  
* IDiffSpread<T>.IsChanged should work correctly now in case of config pins.  
* fixed crash if SetSubType was called with +Infinity/-Infinity.  
* removed Pin<T>.Delete() method. Use Pin<T>.Dispose() instead.