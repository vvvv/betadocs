---
uid: 465f23ca-f2c9-41cd-8a46-dbd6e2a3fff4
---

# Change Log - vvvv40beta23
released on 12 03 10  

## general
* fixed: newly created nodes are now selected  
* fixed texture size types to Int (was double). only FileTexture still uses double. Values between 0..1 are treated as values relative to the image size in file.  
* new option "Paste Within Context" connects pasted nodes to those upward nodes, that were connected with the copied nodes. easy to use, hard to explain  
* major GUI improvements for moving nodes  
* CTRL-Y is now able to reset links  
* win7 fixes: vvvv now shows up in ALT-TAB list and allows its windows to autosize when being dragged to screenborders  
* doubleclick in a patch to create a node followd by '.' now shows accessible .v4ps again  
* rightclicknodelist now shows up correctly even if taskbar not at bottom  

## new nodes
* String2Enum, Enum2String  
## new effects
* NormalsAndDepth.fx writes screen space normals and depth of a scene into a texture  
## fixed nodes
* Find (String) had problems with nil on its inputs (see <a href="http://www.vvvv.org/tiki-view_forum_thread.php?forumId=4&comments_parentId=29923" class="extURL" target="_blank">link</a>).  
* <a href="http://vvvv.org/tiki-view_forum_thread.php?forumId=4&comments_parentId=29952#threadId29961" class="extURL" target="_blank">some XFile bug</a> fixed  
* Writer (File) copes again with relative filenames  
* RandomSpread (Spreads) no longer acts like a saw tooth generator. <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=23609&topics_threshold=0&topics_offset=0&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">bug</a>  
* LFO (Animation) and LFO (Differential) freeze on Zero Period. <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=23609&topics_threshold=0&topics_offset=0&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">bug</a>  
* OSCDecoder (Network): had problems with unpacking cascaded bundles  
* Copier (File) now also copies files that are currently in use  
* VertexBuffer (Join): fixes for BlendWeight and BlendIndex inputs  
* CountIndices (Spreads) <a href="http://vvvv.org/tiki-view_forum_thread.php" class="extURL" target="_blank">bug</a> fix  
* switch <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=30394&topics_threshold=0&topics_offset=22&topics_sort_mode=lastPost_desc&topics_find=&forumId=4" class="extURL" target="_blank">fix</a>  
## changed nodes
* VideoTexture (EX9.Texture VMR9), VideoTexture (EX9.Texture VMR9 YUVMixingMode), VideoOut (DShow9) have a new output named *Pixel Aspect*  
* Ord2Enum has new output: EnumName  
* Fiducial (FreeFrame DShow9): renamed ID output to "Fiducial ID"  
* DetectObject (FreeFrame DShow9): renamed ID output to "Object ID"  
* Contour (FreeFrame DShow9): got new input "Show Filtered"  
* Contour (FreeFrame DShow9): got new inputs "Show Filtered" and "Reload Mask"  
* DynamicTexture (EX9.Texture String) is now spreadable  
* DynamicTexture (EX9.Texture Value) is now spreadable  
* DynamicTexture (EX9.Texture Color) is now spreadable  
* QRCodeTexture (EX9.Texture) is now spreadable  
* MainLoop (VVVV) got a new input: "Improve Timing Precision" which sets the windows timer to max resolution and uses a much more precise frame rate limiting  
* Keyboard (System Global) has a new "Keyboard Spread" output and has the "KeyCode" output now spreaded  
* Change (String) got an additional pin "Bang On Create"   
## plugins
* plugins support new pins: TextureOutput, RenderStateInput, SamplerStateInput  
* the DimensionNames argument on the CreateValuePin methods finally works (beware: this may brake links to pins that already used those!)  
* plugins that save data in their own inputs don't contribute to the undo buffer anymore. fixes the <a href="http://vvvv.org/tiki-view_forum_thread.php?forumId=22&comments_parentId=29851#threadId29869" class="extURL" target="_blank">problem discussed here</a>  
* Bugfix: IEnumOut inherited IPluginIn instead of IPluginOut (see <a href="http://www.vvvv.org/tiki-view_forum_thread.php?forumId=4&comments_parentId=29922" class="extURL" target="_blank">link</a>).  
