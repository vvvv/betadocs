---
uid: bb064c7c-d45d-4618-9b28-74d4fdca4425
---

# Change Log - vvvv45beta24
released on 16 09 10  

## general
* now requires .net3.5 SP1 to be installed, SlimDX no longer needed   
* new CodeEditor for effects and dynamic nodes (via rightclick on those nodes)  
* dynamic nodes allow for plugins being edited/recompiled at runtime  
* new PluginInterfaces V2 reducing lines of code per plugin typically by 40% + allow custom pin types + some more conveniences see <a href="http://vvvv.org/pluginspecs" class="extURL" target="_blank">http://vvvv.org/pluginspecs</a>  
* new Kommunikator for previewing, saving, uploading screenshots (via Ctrl+3)  
* new WindowSwitcher (via Ctrl+TAB)  
* new NodeBrowser (via doubleclick on patch or Ctrl+N)  
* shortcuts like ALT+1,2,3 and CTRL+1,2,3,W ... now also work on all plugin windows like the Timeliner and the new CodeEditor.  
* loading vertical-horizontal-vertical links <a href="http://vvvv.org/tiki-view_forum_thread.php?forumId=4&comments_parentId=32478" class="extURL" target="_blank">fixed</a>  
* start a link from a pin and end it with middleclick to create a suitable IOBox.  
* red nodes now denote missing addons  
* node icons show weather a node has an associated code, patch or GUI window  
* CTRL+I won't open an endless number of Inspektors anymore, instead it will always bring you up the same. if you still need more use SHIFT+CTRL+I.  
* subfolders in \plugins, \effects can be arbitrarily organized. the directory structure is now ignored.  
* no new ids are generated when simply loading a patch  
* string-pins on modules now treat paths as relative to their parent patch  

## new nodes
* Switch (Node Output)  
* Line (EX9)  

## fixed nodes
* Intersect (3d Mesh Subset Ray) works with GetSlice (Node) now  
* FileStream2 (DShow9) now returns correcty position after a seek  
* Queue (EX9.Texture) <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=31087&topics_threshold=0&topics_offset=11&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">bug</a> fixed  
* Input Switches <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=31318&topics_threshold=0&topics_offset=0&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">bug</a> fixed  
* GlyphInfo (String) now updates Position correcly if input changed  
* Sift (Value) used first slice of epsilon spread only. <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=31468&topics_threshold=0&topics_offset=0&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">bug</a> fixed.  
* Intersect (Spreads Sets) returned wrong results. [forum:http://vvvv.org/forum/intersect-%28spreads-sets%29-removes-wrong-slices-when-fed-with-an-unordered-list-of-values|bug] fixed.  

## changed nodes
* IOBox (Value Advanced) and value input pins now take a comma as argument separator for expressions (was semi-colon). also if no expression is detected all non-numeric characters are now stripped before trying to convert the input to a number  
* Keyboard (System Window) now has an Enabled input and a KeyCode output.  
* Tokenizer (String) has a new pin called Queue that outputs the currently queued string  
* IOBox (Value Advanced) has a new configuration pin called Digits that defines how many digits are displayed after the dot. Be aware that this setting does not alter the values, it only influences how they are shown. It also does not (yet) influence the stepping size when changing values using the mouse.   
* IsWellformed (XML) has two new Pins: "Validate on Parse" and "Resolve Externals" <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=32549&topics_threshold=0&topics_offset=0&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">lookilooki</a>  
* Cons (Spreads) has a Bin Size output pin now  
* TogEdge (Animation), Change (Animation), Change (String) don't bang on create by default anylonger