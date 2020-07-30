---
uid: 47fbf044-6c6f-4321-ad7e-76feb6401295
---

# change log - vvvv45beta34
released on 21 07 15  

## general 
* fixed performance issue with IOBox (Raw) and large byte streams  
* fixed boygrouping of spreads containing empty strings - see <a href="https://discourse.vvvv.org/t/boygrouping-with-spread-of-strings" class="extURL forum" target="_blank">boygrouping-with-spread-of-strings</a>  
* in case a plugin node crashes during node creation the corresponding node in the patch will stay red  
* dynamic plugins will always include the debug symbols now - easier to attach visual studio that way  
* fix for slow panning patch <a href="https://discourse.vvvv.org/t/new-bugs-in-beta-33.3" class="extURL forum" target="_blank">new-bugs-in-beta-33.3</a>  
* Setup.exe   
  * now also checking for MSVC++ 2012 (needed only for Assimp nodes in addonpack)  
  * fixed check for .net4 under winXP  
* fixed memoryleak with IOBox (Value)  
* fixed Ctrl+G with enum IOBoxes and unicode characters in patchpath <a href="https://discourse.vvvv.org/t/enum-bug)) [forum:ctrl-g-with-non-latin-chars-in-patch-path" class="extURL forum" target="_blank">enum-bug](TODO INTERNALLINK:forum:ctrl-g-with-non-latin-chars-in-patch-path" class="extURL forum" target="_blank">enum-bug) ((forum:ctrl-g-with-non-latin-chars-in-patch-path</a>  
* fixed performance issue for various value nodes in x64 builds  
* updated Sanford.Midi.dll which works now correctly in x64 builds  
* added new command line /clockport to solve port conflicts with multiple instances on the same machine. see <a href="https://discourse.vvvv.org/t/boygroup-and-idehost-with-multiple-vvvv-instance" class="extURL forum" target="_blank">boygroup-and-idehost-with-multiple-vvvv-instance</a>  
* fixed slow window-docking  
* change detection rework for integer and boolean pins. fixes <a href="https://discourse.vvvv.org/t/iobox-ui-bug-with-grid-node" class="extURL forum" target="_blank">iobox-ui-bug-with-grid-node</a>  
* added success pins to division node, mod node and several spectral nodes for reporting a division by zero or a spectral operation on zero elements. <a href="https://discourse.vvvv.org/t/mean-(spectral)-nill" class="extURL forum" target="_blank">mean-(spectral)-nill</a>  
* fix on plugininterface. bug surfaced when writing into input pins. fixes <a href="https://discourse.vvvv.org/t/dedicated-to-timeliner-node" class="extURL forum" target="_blank">dedicated-to-timeliner-node</a>  
* boygrouping: some warning message got more meaningful  

## fixed nodes
* fixed change flag issue in Zip node - see <a href="https://discourse.vvvv.org/t/zip-(string)-doesnt-update-if-spread-count-changed" class="extURL forum" target="_blank">zip-(string)-doesnt-update-if-spread-count-changed</a>  
* fixed Reader (Raw) not being able to read files which were already open in another process  
* fixed memory leak in HTTP (Network Server) - see <a href="https://discourse.vvvv.org/t/memoryleak-in-http-(network-server)" class="extURL forum" target="_blank">memoryleak-in-http-(network-server)</a>  
* fixed sticky mouse cursor on desktop bounds when using cyclic mode in Mouse (Devices Desktop) node  
* Frac (Value) large numbers do not suffer from down casting to integer range and negative whole numbers will not be rounded down anymore. see <a href="https://discourse.vvvv.org/t/frac-real-part-messed-up-in-x64)) and [forum:fraced" class="extURL forum" target="_blank">frac-real-part-messed-up-in-x64](TODO INTERNALLINK:forum:fraced" class="extURL forum" target="_blank">frac-real-part-messed-up-in-x64) and ((forum:fraced</a>  
* fix for HSV join - see <a href="https://discourse.vvvv.org/t/strange-behavior-of-hsv-node" class="extURL forum" target="_blank">strange-behavior-of-hsv-node</a>  
* fix for decay node - see <a href="https://discourse.vvvv.org/t/decay-x86x64-inconsistency" class="extURL forum" target="_blank">decay-x86x64-inconsistency</a>  
* fix for counter node - see <a href="https://discourse.vvvv.org/t/counter-increment-not-interpreted-correctly-in-wrap-mode" class="extURL forum" target="_blank">counter-increment-not-interpreted-correctly-in-wrap-mode</a>  
* fix for linearfilter node in cyclic mode - see <a href="https://discourse.vvvv.org/t/linerafilter-cyclic-bug" class="extURL forum" target="_blank">linerafilter-cyclic-bug</a>  
* fixed Delta output bug of Pot (Value) node  

## changed nodes
* Player (EX9.Texture) will concatenate all files given by multiple directories. Removed the rather strange modulo behavior.  
* performance improvement for Cons (String) and Cons (Raw)  
* Separate (String) <a href="https://discourse.vvvv.org/t/separate-doesn-t-read-last-empty-value" class="extURL forum" target="_blank">separate-doesn-t-read-last-empty-value</a>  
* FileStream (DShow9) now initializes speed correctly <a href="https://discourse.vvvv.org/t/filestream-(dshow9)-not-remembering-its-speed" class="extURL forum" target="_blank">filestream-(dshow9)-not-remembering-its-speed</a>  
* Renderer (EX9) has a new entry in the fullscreen refresh rate called *AsDesktop* which is the new default  
* added Enabled input and Idle output to all camera modules  
* added ParentHandle output to HandleFromPoint (Windows)  

## plugin interface
* added Visibility to IPin/IPin2  
* fixed CheckIfChanged inconsistency reported by <span class="user"><a href="https://vvvv.org/users/velcrome" class="extURL" target="_blank">velcrome</a></span>  
* fixed changed flag issue with streams used as pin group  
* added debug symbols (vvvv.jdbg) to VVVV.Binaries NuGet package  
* added missing StatusChanged event to IPin2 interface (was already present in implementation)  
* fixed the IPin2.IsConnected method  
* fixed <a href="https://discourse.vvvv.org/t/inconsistent-behavior-in-plugin-interface" class="extURL forum" target="_blank">inconsistent-behavior-in-plugin-interface</a>  

## new nodes
* Clean (String Advanced)  
* Percent (Value)  
* FrontFacing (3D)  
* Mouse (Devices Window Cyclic)  
* ScreenInfo (Windows)  
* Window (Windows Client)