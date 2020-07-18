---
uid: e4a13c8e-8892-441a-946a-60228f13a5be
---

# Change Log - vvvv40beta22
released on 24 12 09  

## general
* the Renderer (EX9) settings enumerations now show up in the Info (Enumeration) output when there is at least one Renderer (EX9) open.  
* boygrouping:  
  * clients now can be controlled from more than one server  
  * broadcast IPs and network ports can be specified  
  * bug with doubled patches on clients fixed  
  * massive performance gain with transmitting large spreads of values  
* bug fix: changes over node pins (like with Switch (Node Input) ) now always result in reevaluation of the downwards connected node   
* Loading in Background now is much smoother  
* Effect-Editor shows Find-Selections correctly and no longer sends keyboard strokes to Keyboard (Window)  
* string-pins now accept smb:// and url-encoded URLs  
* vvvv should not prevent windows from shutting down anymore  
* changing linkstyle to bezier now will be saved  
* no more double connections possible on inputs  
* <a href="http://vvvv.org/tiki-view_forum_thread.php?forumId=4&comments_parentId=27782#threadId27954" class="extURL" target="_blank">duplicate bug</a> fixed  
* middle mouseclick to set descriptive name now also works on IOBox (Node)  
* nodes are no longer deselected on middleclicking a patch  
* newly created nodes are now selected  

## new nodes
* MidiShort (Devices) Recieves all midi messages and outputs the raw data  
* MidiSysex (Devices) Recieves midi system exclusive messages  
* Find (String) Returns the number of occurences of a substring in a string and the 0-based position-index of the first character of the substring in the string. The comparison is case-sensitive.  
* FileStream2 (DShow9): like FileStream but is supposed to load movies without hickups.  
* Convert (String) to convert between different string encodings  

## fixed nodes
* Stallone (Spreads, String and Color) evaluates correctly if input or output pin count is changed. See <a href="http://vvvv.org/tiki-view_forum_thread.php?forumId=4&comments_parentId=25704" class="extURL" target="_blank">link</a>.  
* Keymatch (String) renames its pins correctly.  
* Info (Enumerations): had a memory leak  
* XFile (EX9.Geometry Load): bugged at loading meshes with more than 1000 subsets  
* XFile (EX9.Geometry Load): bugged when file not found  
* Effect (EX9.Effect): fixed problem with array pins  
* Renderer (Flash) now sends keyboard strokes to Keyboard (Window)  
* Renderer (GDI) now sends keyboard strokes to Keyboard (Window)  
* Reader (File) now allows to choose not only .txt but also .csv, .xml, .dtd, .html files per default  
* XPath (XML) now preserves whitespace  
* SpellValue (String) in modes english and german now returns strings trimmed from whitespace  
* Division by zero occured in SetSlice nodes. See <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=28209&topics_threshold=0&topics_offset=1&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">link</a>.  
* some S/R (Node) Issue fixed.  
* IP (Network) no longer consumes unnecessary juice  
* unmade Kalle (VVVV) a singleton  
* unmade Keyboard (System Global) a singleton  
* TogEdge (Animation) <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=24311&topics_threshold=0&topics_offset=5&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">Bug </a>fix  
* VideoIn (DShow9): fixed crashes with devices that have triggerbuttons  
* Pipet (EX9.Texture) now has working "Enabled" pin instead of non-working "Force Refresh"  
* Vector (Join/Split) nodes no longer cause value inaccuracies  
* Sift (String): fixed problems with nil inputs  
* Keyboard (System Window): now reads TAB, BACK, DELETE and INSERT keys correctly  
* QRCodeTexture (EX9.Texture) now handles relative paths correctly  

## changed nodes
* XFile (EX9.Geometry Load) got spreadable   
* Renderer (TTY) now has a string output wich outputs the last message.   
* Renderer (TTY) has a hidden pin "Show Timestamp" (for better debugging it puts a timestamp before every message)  
* Writer (File) hass a hidden pin "Create Directory" if it does not extist.  
* Integral (Spreads) now works on bins  
* Count (EX9.Geometry) got additional pins: *Subset VertexCount* and *Subset FaceCount*   
* FileTexture (EX9.Texture) got additional *Preload* pin to actually preload textures into VideoMemory.  
* FileTexture (EX9.Texture) has new mipmap behaviour: In the new mode *Automatic* it behaves like *From File* for .dds textures, but creates all mipmaps for all other file formats. *Automatic* is the new default.  
* FileTexture (EX9.Texture) and XFile (EX9.Geometry Load) now have a new pin *Use Preloaded Item*. Using this option only preloaded files will be used while all settings are ignored. That way you can have one place where you specify how to load the resources and reference them at other places in your system.  
* Map (Value Interval): better performance  
* Info (EX9.Texture) now also can report about properties of the original image file, useful for when you change its size on loading to save memory. it also outputs the original file format  
* texture file formats ".tga" and ".ppm" added (for use with DynamicTexture (EX9.Texture String) and Writer (EX9.Texture))  
* CurrentTime (Astronomy) now outputs (in addition to current local time) current UTC/GMT, Time Zone, Time Zone Name, Daylight Saving Time   
* DShow9 Source nodes have a new hidden Input *Adjust System Time* mainly useful for FileStream to sync playback on multiple streams in subframe (ie. millisecond) steps  
* AsVideo (DShow9) got new *Enabled* pin and its *Reference Clock* now defaults to: None  
* SubDir (File) is now able to ouput all sublevels of the specified directories  
* VertexBuffer (Join): added BlendIndices input  
* Contour (FreeFrame DShow9): renamed ID output to "Contours ID"  

## plugins
* Bugfix: vvvv no longer crashes and plugin nodes no longer stop working after reloading a patch.  
* Bugfix: The method PluginHost.DeletePin didn't delete input pins of type String/Color/Node.  
* Host.GetCurrentTime now returns a fixed time per frame  
* plugins are now being loaded even from subdirectories of \plugin  
* plugins now also load with relative paths + classname specified