---
uid: 161bc945-401a-4d9d-bc63-191c6b80ee67
---

# Change Log - vvvv45beta25
released on 24 12 10  
## general
* caching now saves only one file into the application data/temp dir  
* slightly better startup performance due to lazy loading of dynamic plugins  
* fixed a crash of vvvv if a plugin tried to log from a different thread than the main thread  
* fixed various memory leaks related to plugins  
* dynamic plugins copy locally referenced assemblies to the output directory on compile, so it should not be necessary anymore to put external dependencies in the bin/managed or plugins folder of vvvv.  
* fixed a few threading issues regarding background parsing of c# projects and documents  
* pluginwindows now hide correctly when sent to box (ALT+2) while their parent window is hidden  
* plugin nodes are colored red in debug mode (ctrl+F9) if they throw runtime errors.  
* debug mode now consistently colors nodes throwing errors  
* only IOBox is selected after creating it with middleclick while making a connection  
* duplicate within context added for patcheditor (keeps input links on duplicated nodes)  
* file/dir open/save dialogs now open with the correct initial file/dir again  
* better integration of code editor by using vvvv's window management for tabbing  
* ctrl+click on a dynamic node brings up a dialog to choose which source file to open  
* code editor opens up on a per node basis. so it only shows runtime errors of a specific node.  
* string pins of subtype filename/directory now resolve environmentvariables like %USERPROFILE%  
* new window: Finder (Ctrl+F)  
* windowswitcher now based on Finder and also opens with ctrl+shift+tab  
* new window: ProjectExplorer (Ctrl+J)  
* project explorer displays project files of dynamic plugins and effects. it can be used to add/remove documents/references to a dynamic plugin and set the build configuration in order to debug a dynamic plugin in an external IDE like sharp develop or visual studio.  
* optimized queue node.  
* dynamic plugins don't need to be in vvvv/plugins anymore.  
* cloning a template will use the path of the active patch suffixed with plugins/effects depending on the type of template.  
* fix: cloning a dynamic plugin should handle illegal c# class name characters properly.  
* if not necessary project files of dynamic plugins are not loaded by vvvv on node creation.  
* fix: code editor should show errors in included fxh files too.  
* if a node referenced by a v4p file can't be found or in case of dynamic plugins can't be compiled it should show up as a red node. see [nodes and paths](TODO INTERNALLINK:nodes and paths).  
* fix: it shouldn't be a problem anymore to change the plugin info of a dynamic plugin during runtime. changing the systemname will result in a red node.  

## plugininterface
* better performance when deleting plugin/dynamic nodes (no more forcing of garbage collection)  
* fixed memory leak in reloading of dynamic nodes  
* generic output pin of type T registers GUIDs of T and all implemented interfaces and subclasses. for example an output of type Apple should be connectable to an input of type Fruit now.  
* colorpins are now using their subtypes correctly  
* texture-output-pins are now spreadable  
* ISpread<T> shouldn't lose data if slicecount is increased or decreased  
* added new argument IPin to IPinUpdater.Connect/Disconnect methods  
* fix: setting slice count of GenericOutputPin to 0 didn't have any effect  
* fix: divide by zero in InputBinSpread  
* introduced new IPluginHost2 which implements IPluginHost and INode.  
* removed all wrapper pin classes in V2. reduces overhead a little and should therefore bring little performance improvements.  
* moved Pin<T> and DiffPin<T> from VVVV.Hosting to VVVV.PluginInterfaces.V2. it's now possible to import Pin<T> instead of ISpread<T> if advanced features like Connected / Disconnected events are required.  
* fix: SetRenderState/SetSamplerState and SetTextureStageState crashed since beta24. <span class="node">Text (EX9)</span> used those methods so hopefully this fixes some strange behaviours reported by various users.  
* methods of IPinUpdater weren't called if used in conjunction with V1 plugin  
* reduced overhead a little in call to Evaluate method of plugin  
* fix: if a plugin only implemented IPluginBase Update on Config pins wasn't called.  
* fix: plugin input pins were deleted on recompile if plugin was evaluated each frame (for example if it was selected by inspektor), causing runtime exceptions.  
* fix: <a href="http://vvvv.org/forum/enum-pin-in-v2-always-only-slicecount-of-1" class="extURL" target="_blank">http://vvvv.org/forum/enum-pin-in-v2-always-only-slicecount-of-1</a>  
* Added extension method ISpread.Clone() and added extension method ISpread.AssignFrom<T>(IList<T>).  
* added property Buffer to Spread (use with caution).  
* did a complete overhaul of the v2 pin implementations. much better memory management, far less garbage collections necessary -> hopefully far less glitches.  
* added pin attribute Lazy to ISpread<ISpread<T>>. should be used in case one is only interested in a subset of the input. good example would be a getslice node.  
* fix: v2 plugins use plugin host to log instead of default logger.  
* Fixed overflow exception in RGBAColor when converting to System.Drawing.Color.  
* fix: ISpread<ISpread<T>> should handle spread of negative bin sizes correctly.  
* fix: v1 plugins weren't properly disposed if SetPluginHost method crashed.  
* StringOutput pin only writes to internal pin if necessary in order to avoid expensive marshalling costs.  
* introduced new INode2 interface which can be used by plugin writers to inspect the graph of vvvv. see IHDEHost.RootNode  

## fixed nodes
* <span class="node">Frac (Value)</span> can output whole parts up to MaxFloat  
* <span class="node">QRCodeTexture (EX9.Texture)</span> now only computes when one of its input changes and its textures are now accepted in Queue (EX9.Texture)  
* <span class="node">Cons (EX9.Texture)</span> now evaluates correctly if first pins are nil.  
* <span class="node">Mesh (EX9.Geometry Split)</span> now reports vertexbuffer downstream correctly if input has empty or nil mesh  
* <span class="node">AsString (Value)</span> now deals with a spreaded enum correctly