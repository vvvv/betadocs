---
uid: c9fde805-3d4a-4f39-b1b1-0e28e1830ea2
---

# Change Log - vvvv45beta25.1
released on 18 02 11  
## general
* now with crack.exe (replacing uninstall.exe). run once! (as you do..)  
  * no more registration of .v4p filetype on starting vvvv.exe. now only via crack!  
* splashscreen now shows up when starting patch via doubleclick  
* subtype and iobox bug fixes  
  * especially enum bugs. additionally enum features: invalid enum entries now lead to red nodes. useful e.g. when you have a <span class="node">r (Value)</span> to a channel that doesn't exist (e.g. the patch with the corrsponding sender might not be open)  
* effect enums now update correctly when code changed  
* added vvvv.exe.config file to support debugging sd4/vs2010.  
* fixed the EStringError when starting without arguments out of sd3.  
* no accidental root saving any longer  
* better help on using contributions in root  
* modules again open in a window when opened by windows explorer  
* correctly getting dummy node after changing nodename of a plugin node   
* replacing nodes also changes legacy "nodename" attribute in "node" tag <a href="https://discourse.vvvv.org/t/beta25-iobox-(color)-opens-as-iobox-(value-advanced)-in-older-versions" class="extURL forum" target="_blank">beta25-iobox-(color)-opens-as-iobox-(value-advanced)-in-older-versions</a>  
* it should no longer be a problem to work with projects of same filename but in different locations. for example (vvvv/effects/file1.fx and patches/foo/bar/file1.fx).  
* if a cached nodeinfo is invalid (for example file is corrupted) a red node will appear instead of a gray one without any pins.  
* GUI plugin templates added  
* nice help files for templates added  
* vvvv shouldn't block windows from shutting down if started with /shutup argument or no patch is edited or user doesn't chancel the quit command: <a href="https://discourse.vvvv.org/t/vvvv-prevents-windows-shutting-down-(stillagain)" class="extURL forum" target="_blank">vvvv-prevents-windows-shutting-down-(stillagain)</a>  
* .csproj now available in "OpenInPatch" dialog  
* dtd updated  

## GUI
###  Finder & Window Switcher
* fixed serveral memory leaks  
* other bug fixes  
* invalid enum entries now also can be found through the finder: the surrounding patch also gets red.  
###  NodeBrowser
* now includes username-tags again  
* clicking in a patch to hide the browser now creates a comment   
* drag'n'drop works again from standalone version  
###  ProjectExplorer
* the *Add Reference* dialog of C# projects can now browse for assemblies (additional to selecting assemblies from the GAC)  
* now supports adding existing documents to a project.  
* should give a hint if a referenced file is missing.  
* caused vvvv to crash if more than one reference was added at once.  
###  CodeEditor
* fixed copy and paste issues introduced in beta25  
* Ctrl+F invokes correct find-monolog again  
* indents brackets correctly.  
* supports auto indentation (Ctrl + I).  
* does not show runtime errors of previously compiled assembly.  
* handles local/global ("" vs <>) includes in .fx files correctly.  
  * effect files use directory of vvvv.exe as global include path (for e.g. #include <effects/foo.fxh>).  
  * only locally referenced fx files are copied in a clone operation.  
* fixed several memory leaks  
###  PatchEditor
* while making a connection in a patch space+rightclick simulates a middleclick  
* scroll position is respected on drag drop again  
* undoing replaced nodes works again <a href="https://discourse.vvvv.org/t/undo-(ctrl+z)-and-exchanged-nodes" class="extURL forum" target="_blank">undo-(ctrl+z)-and-exchanged-nodes</a>  
* patches now load with black background if so saved  

## fixed nodes
* <span class="node">Random (Value)</span> is more random now between multiple instances  
* <span class="node">NodeList (VVVV)</span> better performance when adding a search path  
* Sift (Value) fixed memory leak. See [http://vvvv.org/forum/sift-memory-leak].  
* <span class="node">IOBox (String)</span>: fixed drag'n drop on it.  
* <span class="node">IOBox (String)</span>: fixed "very long iobox" issue after drag drop. see <a href="https://discourse.vvvv.org/t/beta25-dragdrop-a-path-from-explorer-adress-bar-to-io-%28string%29-bug" class="extURL forum" target="_blank">beta25-dragdrop-a-path-from-explorer-adress-bar-to-io-%28string%29-bug</a>.  
* <span class="node">Cons (EX9.Texture)</span> fixed, see <a href="https://discourse.vvvv.org/t/spreaded-filetexture-and-cons-node-bug-in-beta25" class="extURL forum" target="_blank">spreaded-filetexture-and-cons-node-bug-in-beta25</a>  
* <span class="node">SharedMemory (Windows)</span> output now returns complete string  
* <span class="node">CreateNode (VVVV)</span>: QuerySave bug fix  
* <span class="node">Count (EX9.Geometry)</span>: now updates if any of the upstream subsets changed  
* <span class="node">BoundingBox (EX9.Geometry)</span>: can now deal with meshes that have more subsets than attributetable entries.  

## plugininterface
* fix: generic input pin didn't fetch new upstream interface if upstream node was recompiled.  
* added BinSize property to InputAttribute.  
* if creation of a plugin fails treat it as runtime error instead of creating a red node indicating that the plugin is missing.  
* do not use MEF to scan an assembly for plugins. use it only on plugin creation. better performance and fixes several issues, if for example classes attributed with a PluginInfo didn't implement IPluginBase or a PluginInfo was defined twice.  
* IDiffSpread<ISpread<T>> implementations didn't fire changed event if bin size changed.  
* added new extension methods Add, AddRange, Remove, RemoveAt, RemoveAll, RemoveRange, GetRange, IndexOf, Insert, InsertRange to ISpread<T>.  

##  new modules
* OpenURL (Network) opens a link or file with the systems default application