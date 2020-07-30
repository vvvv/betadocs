---
uid: 53415dec-f527-4181-92bd-23c5e7578387
---

# Change Log - vvvv33beta6
released on  24 12 03  

## general:
* undo is more convenient now: all actions performed within a certain time span (like fast value changes by dragging a pin) are treated as one action. these groups of actions can be undone or redone in an animated way (by default 10 times faster than originally performed)  
* you can now use freeframe video effects within vvvv.  freeframe is a standard for opensource videoeffects. see: <a href="http://freeframe.sourceforge.net/" class="extURL" target="_blank">http://freeframe.sourceforge.net/</a>. you can currently get plugins from: <a href="http://sourceforge.net/project/showfiles.php?group_id=66712&package_id=66575&release_id=176159" class="extURL" target="_blank">http://sourceforge.net/project/showfiles.php?group_id=66712&package_id=66575&release_id=176159</a>  ResolumeFreeFramePlugins and <a href="http://www.petewarden.com" class="extURL" target="_blank">http://www.petewarden.com</a> (TransZenDent/FreeFrame FX) the plugins come in form of *.dll files. put them in a directory called /freeframe that resides in the same directory as vvvv.exe. restart. on restart the effects are available under the new category 'freeframe'  run setup.exe to register the directshow wrapper filter. go to http://www.petewarden.com/PetesPlugins_FreeFrame1.07.zip  

## new nodes
* added: Undo (VVVV): tweak the undo behaviour. (try to increase the timespan dramatically so that the whole patch session is treated like one action. experiment with "Undo Speed", "Redo Speed")  
* added: CAR (String)  
* added: VVVV (VVVV): Show/Hide VVVV in the Taskbar and the Tray and give it a title  
* fixed: (again) VideoTexture (Textures9 DShow9) did not work with certain graphic card / driver versions  
* fixed: VideoIn (DShow9): now works even with devices that don't offer a list of framerates to choose from  
* fixed: vvvv used to crash on startup if started with /r and following a relative path   
* fixed: FFT (DShow9): will now run in fullscreen  
* improved: FileReader, FileWriter: if "Do Read"/"Do Write" is 1 the file is read/written every frame. use TogEdge to prevent this  
* improved: GridSplit, GridPick: coordinate system updated to (-0.5/-0.5)..(0.5/0.5)   (see help files)  
* improved: GridSplit, GridPick:cells are ordered left->right, up->down  
* improved: GridSplit, GridPick:point outside grid (GridPick) -> cell index = -1 -> resulting cell: (0,0,0,0) (GridSplit)  
* improved: Mouse (System Global): buttons retrieve values: 0=no click, 1=click, 2=double click  
* improved: Add (String): faster. different intersperse for every outputslice only  
* improved: Keyboard (System Global): send key strokes to the system with 'Keyboard Input'  
* improved: Tokenizer (String): was too slow; got UpdatePin for explicit updates  
* improved: Windows (Windows): coordinate system updated to (-0.5/-0.5)..(0.5/0.5)  
* improved: VideoIn (DShow9): got new pins for 'Analog Video Standard' and 'Analog Video Inputs' to support analog video capturecards  
* improved: VideoOut (DShow9): now has DeinterlaceOptions (which actually don't seem to work yet)  