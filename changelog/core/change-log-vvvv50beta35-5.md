---
uid: daee5852-e98b-40ff-9d79-2de382c1d7f4
---

# Change Log - vvvv50beta35.5
released on 19 04 16  

##  VVVV
* layout changes don't lead to a changed patch file anymore.  
* enums: get notified again whenever an entry is not available.  
* improved error-logging in case a ~temp file is written  
* cloning vl Template (Value Stateless) now works correctly  
* improvements and additions for <a href="https://vvvv.org/blog/editing-framework-update" class="extURL blog" target="_blank">the EditingFramework</a>  
* s/r channels sorted in pop up  
* r nodes don't forget last sender when sender got deleted  

### new nodes
* HTTPGet (Network) replacing now legacy HTTP (Network Get)  
* HTTPPost (Network) replacing now legacy HTTP (Network Post)  
* Reader (2d BezierSpline)  
* Reader (3d BezierSpline)  
* Writer (2d BezierSpline)  
* Writer (3d BezierSpline)  

### fixed nodes
* S+H (Transform) spreading now works correctly  
* MidiTrack (Midi) performance improvements and fixes for files including sysex messages  
* performance improvements for TUIO nodes  
* fixed AreEqual (Test Value) not testing the slice count (link was missing)  
* fixed evaluation order of Writer (Raw), Mover (File) and Copier (File)  
* [node:Select](TODO INTERNALLINK:node:Select) & [node:SetSpread](TODO INTERNALLINK:node:SetSpread) in pretty much all versions now can deal with an empty spread at <span class="pin">Select</span>  
* <span class="pin">Technique</span> on EX9 effects: not red when null  

### plugin interface
* fixed default connection handler always returning true (introduced in b35) + other refinements.  
* fixed crash in CyclicStreamReader - [https://discourse.vvvv.org/t/setspread-problem-with-count/14820]  
* added implementations for IStream.CopyTo methods used by S+H (Raw) - fixes S+H (Raw) not working on upstream native nodes  
* fixed the generic SetSlice plugin - [https://discourse.vvvv.org/t/multidim-assignfrom/14850]  
* fix on registering GUIDs. added IPluginHost.RegisterType to be able to properly register each GUID with name  
* builtin pins register themselves in a way, so that you can cast the object returned from GetUpStreamInterface to IValueData(..). By that you can write a custom connection handler that interacts with builtin pins.  

##  VL
* auto backups are now stored in Documents\VL  
* added menu entry to open auto backups folder  
* tabs of active document now visually distinguishable from others  
* prev/next navigation now includes operations in a patch  
* added "Reset To Defaults" for settings  
* tooltip in NodeBrowser now shows more infos  
* added hint-tooltips for certain ui elements  
* IOBox now rasters to stepsize (same behavior as in vvvv)  
* fixed problem with elements in document-patch not aligning on CTRL+L  
* added 'open' button to IOBox (Path)  
* dependency menu now shows loaded vs. referenced nuget versions  
* better adaptive node errors  
* fixed "Surround With .." for when other nodes with that name are in scope.  
* fixed some crashes involved in creating a new vl document, saving it  

## new nodes
* new category XML for all your xml/json needs  
* new reactive nodes for async/concurrent event handling  
* new midi nodes for event based midi processing  
* Contains (Spread) checks whether an element is in the spread  
* IfAnyChanged regions in Lib.Experimental, calculates and caches a result if any input value has changed  
* HardwareChanged/Added/Removed nodes to get notified when the device configuration changes  

### changes/fixes
* assigning pin to another operation keeps type annotation and default value  
* performance improvements for OSC nodes  
* fixed generated target code for if region with output connected to exact one upstream pin  
* fields which somehow made it into a stateless context will now also be removed when synchronizing the model with the symbols (Ctrl+E)  
* fixed pasting of pins from or to sub patches - [https://discourse.vvvv.org/t/pasting-from-one-vl-doc-to-another-looses-pads/14787]  
* newly created regions will not auto sort their pins anymore  
* fixed linking into process regions showing error on link that upstream hub is not on same moment as downstream hub   
* moving pins in a delegate will trigger recompile  
* VL now has dynamic enumerations, i.e. for device driver selections  
