---
uid: 2da1490b-8c63-40f6-81f2-90f6e9a34faf
---

# change log - vvvv50beta35.7
released on 20 06 17  

## VVVV
* setup.exe now checks for 2017 instead of 2015 vc++ redistributables  
* splashscreen, tabs, finder are now dpi-aware  
* Enums now pay more attention to the name of the entry than its index. In corner cases this should meet expectations more closely.   
* added Red links to flag links between mismatching pins. Invalid links are stored in patches so that they can be reestablished when they match again. This should be helpful for dynamic plugin and VL development. Red links also mark all parent patches red so that they can be found easily.  
* nodebrowser accepts patches again if they start with a lower-case letter  
* Girlpower includes now the Molecule Viewer example app (see it in girlpower/Games/).  
* added TransformVVVV to VMath in SDK  
* added "Save all patches" (even those marked as unchanged). Useful for saving window layout.  
* Scrolling in patches not perceived as a change  
* cloning modules now does not inlude a trailing space if no version is set  
* fix for Finder with vl nodes  

### new nodes
* GetSlice added for Enum, Transform and Raw  
* Universe (Network Join/Split) to work with the ArtNet nodes  
* CR, LF and CRLF newline modules  

### fixed nodes
* BezierSplines can be loaded/saved using the Reader (2d/3d BezierSpline), Writer (2d/3d BezierSpline).  
* Enum shuffling nodes finally behave as wanted: CAR, CDR, Cons, GetSpread, Select, SetSlice, SetSpread, Unzip, Zip.   
* fixed problem with Timeliner on high-dpi where tracks would get higher everytime they are loaded  
* plugin-nodes that have no UI no longer can be put into boxed mode  
* MJpegStream module no longer takes extra port which makes it work with all urls  
* Fixed spreadability of the DigitalRead (Firmata)and the VL.IO.Firmata pack got its own girlpower folder.  
* some Text (EX9) fix  

### changed nodes
* All Editors from the [editing-framework](TODO INTERNALLINK:Editing Framework) have a Gizmo manipulator.  
* Spout nodes now handle up to 40 channels  
* ArtNet nodes now take a single Universe value instead of Net/Subnet/Universe  

### plugin interface
* SetSubType on INodeIn in with several GUIDs is interpreted as "or" to make Box2d run again.  
* Node factories will be disposed of properly on vvvv shut down.  
* Added new property IHDEHost.Version which returns the currently running vvvv version.  
* Updated SharpDX to version 4.0.1  

## VL
### general
* Removed the restriction that patches exposed to VVVV need to be classes.  
* VL packages which expose nodes to VVVV will also be released with a nodelist.xml file now. Improves the vvvv startup time.  
* In case a stateful region is available on a node the choices in the nodebrowser will now show "Region" and "Region (Stateless)".  
* Fixed linking to a process inside a nested region - such a link was red before with the invalid error message that the source and the sink are on different operations.  
* Added a little explanation to the AsyncTask region what happens when triggering the Abort input.  
* Fixed crash in backend when building a patch with just one generic output pin.  
* Backup reminder when opening with new VL version  
* When saving under new file name, all open documents referencing our document now reference the new document - via the new file name.  
* updated JSON.NET to 10.0.2  
* The "Loop" is now called "Repeat", so we can now say VL comes with two kinds of loops, "Repeat" and "ForEach"  
* added solution explorer window (CTRL + J) to inspect all documents + patches  
* Fixed a few crashes when restoring the state of running patches  
* Less machine-made changes in patches. This is good when evaluating your changes via a diff tool.  
* Comments are allowed outside dataflow context. (e.g. the Document root patch)  
* Less restrictive naming rules. Categories and therefore "Group"-elements can now be named "2D" to be able to easily contribute to the Category.  
* Autobackup only backups documents that have been openened in the editor  
* documents last saved with an older version now show a green hint-icon in the ActiveDocument menu  
* documents last saved with a newer version now show a red-hint-icon in the ActiveDocument menu  
* Fixed null pointer when using parameter = null in imported C# node  
* Fixed linking of process state output into a region   

### ui features/changes/fixes
* Quad menu -> About and ActiveDocument menu now show a version  
* Quite some tweaks and fixes on node browser  
* comments can now wordwrap  
* CTRL+F to find elements in a patch  
* CTRL+SHIFT+F to find elements globally  
* IO boxes inside if regions didn't report their dimensions to the UI  
* press SHIFT to constrain moving nodes to x/y  
* middleclick now deletes links even if not selected  
* patch metadata (CTRL+M) is now saved correctly   
* Duplication (Ctrl+D) of groups works now  
* Duplicate (CTRL+D) of selections now offsets according to last move (as in vvvv)  
* node-sizing pick-area is now zoom-aware  
* typeannotation editor is now zoom-aware  
* Undo wasn't always available when working in the patch explorer  
* The assign menu entries will be disabled in case they don't have any effect - https://discourse.vvvv.org/t/process-in-member-op/15128  
* Fixed performance issues of menu when system has .NET 4.7 installed  
* Middle click on border control point behaves correctly  
* Double click while linking opens node browser  
* CTRL + left click while linking creates pin  
* SHIFT + left click while linking creates pad  
* CTRL + click while linking in IF or LOOP creates accumulator proxy  
* CTRL + SHIFT click while linking in LOOP creates splicer proxy  
* links snap to nearest accepting data hub while linking  
* Fixed flickering tool tip on link when link had a warning  
* More robust region size computation. Allows very small regions. Delayed auto-compacting: to trigger this move an element inside.  
* Force dragging into/out-of regions is now on SPACE  
* Force dragging elements into/out-of regions more responsive  
* Force connection while linking is now in SPACE  
* Force connection while linking highlights accepting hubs  
* Save dialog fix (shouldn't pop up when already everything is saved)  
* Boolean OutBoxes show every bang if UI can draw faster than 67ms  
* SHIFT + double click or SHIFT + double right click on link inserts pad into link  

## fixed nodes
* file readers/writers now don't block the file after their operation  
* Matrix (Join) assigns elements correctly  
* ForEach (Reactive) resets thread safe  
* Filter (Animation) doesn't output NaN when time set to 0  

## new nodes
* GetValues for matrix  
* Integer Counters   
* Conversion nodes (e.g. ToFloat32) now also Adaptive (any number value is ok), just to make using them less of a pain  
* ToQuadTransformatio and FromQuadTransformation for Rectangle  
* RandomSpread (2d/3d)  
* OrderBy (Spreads)  
* RecursiveTree  
* Dir and SubDir  
* AND/OR (Spectral)  
* Debug, Repeat, Retry, BackoffAndRetry, Merge (Many) and OnErrorResumeNext in the Reactive category  
* The above and more in the Reactive.Observable category exposed by the VL.DevLib package  

### experimental
 * ManageProcess lets you enable a process and reset it.