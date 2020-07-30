---
uid: e673e77b-8293-40c6-a128-49a204a34da4
---

# Change Log - vvvv45beta27
released on 24 12 11  

## general
* vvvv now requires .net4.0 and msvc++ 2010 runtime components (as reported in crack.exe)  
* crack runs without that annoying sound  
* simpler directory structure for vvvv:  
> 
 \addonpack
 \girlpower 
 \lib
 \licenses
  
* performance tuning on basic graph evaluation strategies and gui  
* patches now can be disabled by setting the <span class="pin">Evaluate</span>) avaible on each patch to zero. by default this guy is only visible in the inspector, but it is an input that you can make visible in the patch and use it to dynamically disable patches.    
* worked on device handling, removed quite some bugs popping up in texture feedback situations  
* while texture feedbacks still work with <span class="node">Queue (EX9.Texture)</span> we recommend to use the new node <span class="node">FrameDelay (EX9.Texture)</span> to do the feedback. At some point in the future we might not allow shortcut without a framedelay anylonger. Only with the FrameDelay nodes a clear cut between frames is possible  
* reworked a lot of helppatches  
* all assets (images, xfiles,..) shipping with vvvv are now in \lib\assets  
* fixed issue introduced with beta26 that uncaught exceptions popped up in error dialog  
* exceptions thrown during render pass will be shown in ExceptionDialog if enabled  
* fixed some boygrouping issues  
* fixed issue where dynamic plugins wouldn't get reloaded after recompile  
* textures created by plugins now work in texture buffer nodes, like <span class="node">Buffer (EX9.Texture)</span> or new <span class="node">FrameDelay (EX9.Texture)</span>  
* times where errors could result in a major system hang - where you need to log out and all that - shouldn't occur anylonger.  
* singleton bug fix: couldn't replace <span class="node">Mouse (System Global)</span> with <span class="node">Mouse (System Window)</span>. resulted in both nodes on top of each other.  
* dynamic textures and meshes don't spam the <span class="node"> Renderer (TTY)</span> anylonger  

## gui
* when creating an iobox via middleclick (while making a connection) linkpoints are now kept.  
* fixed two occasions where finder would collapse  
* last visible window can now not be boxed/hidden  
* now when canceling OpenPatch from the QuitOptionsDialog the dialog pops up again  
* effect editor didn't show all errors from effect compiler in some cases  
* dynamic nodes (fx/c#) should turn red if code contains syntax errors  
* fixed issue that nodes wouldn't even show up as a "red missing" node if error occured during node creation  
* gui performance tuning. visible patches shouldn't be that bad any longer...  
* debug mode shows timings now in microseconds. was in 0.1 milliseconds before.  
* in NodeBrowser the sorting of nodes is now back to normal  
* OpenInPatch now places node correctly even when patch is scrolled  
* CodeEditor no longers zooms in when writing a } on frensh keyboards  
* pressing F1 on CodeEditor now opens related wikipage  

## fixed nodes
* <span class="node">Mouse (System Global)</span> is no singleton anylonger  
* <span class="node">TCP (Network Server)</span> now copes with nil inputs  
* <span class="node">Switch (Color Output)</span> now spreads correctly  
* <span class="node">CreateNode (VVVV)</span> can now create patches in same dir as its parent  
* <span class="node">WavePlayer (DShow9)</span> now closes filehandles to files it attempts but fails to read  
* <span class="node">Text (EX9)</span>   
  * didn't cleanup properly after a device was destroyed. note however that this does not address the issue posted here: <a href="https://discourse.vvvv.org/t/memoryleak-in-text-(ex9)-plugin" class="extURL forum" target="_blank">memoryleak-in-text-(ex9)-plugin</a>  
  * disabling/enabling should not lead to a frame rate drop anymore  
  * size output fixed  
* <span class="node">GetSlice (Spreads)</span> bug fix: <a href="https://discourse.vvvv.org/t/getslice-bug" class="extURL forum" target="_blank">getslice-bug</a>  
* <span class="node">Queue (EX9.Texture)</span> should do again...  
* <span class="node">Buffer (EX9.Texture)</span> should do again...: <a href="https://discourse.vvvv.org/t/video-mem-recorder-texture-buffer-bug" class="extURL forum" target="_blank">video-mem-recorder-texture-buffer-bug</a>  
* primitve layer nodes like <span class="node">Quad (DX9)</span> should use 16bit indexbuffers again when graphics card can't cope with 32 bit. should fix issues on computers like netbooks.   
* <span class="node">SharedMemory (DShow9)</span> not supposed to crash anymore when changing size of source  
* <span class="node">Info (Enumerations)</span> memleak fixed  
* <span class="node">Intersect (EX9.Geometry Mesh Ray Legacy)</span> has ray orientation on x-axis again  

## changed nodes
* <span class="node">Renderer (EX9)</span> has new default 'AsDesktop' for <span class="pin">Fullscreen Dimensions</span>, it sets the fullscreen resolution automatically to the size of the desktop on which the renderer window is. Also it's now supposed not t flicker white when going fullscreen  
* <span class="node">Text (EX9)</span> added pins to control font caching and preloading behaviour  
* <span class="node">GetPatch (VVVV)</span> now comes with a pin "Patch Changes" displaying the message - a XML snippet - that was last sent to a patch.  
* <span class="node">IOBox (String)</span> now allows copying binary strings on dblclick  

## new nodes
* a set of nodes to handle SVG graphics  
* <span class="node">Framedelay (EX9.Texture)</span> added. the new standard way of doing texture feedbacks.  
* <span class="node">OnResume (VVVV)</span> added. it bangs on reactivation of patch evaluation...  

## modules
* <span class="node">Camera (Transform Softimage)</span> got a performance tune. keyboard only reacts when a dx rendeer is active  

## plugininterface
* new property ParentNode in IPin and INode for easier graph traversal in plugins  
* new method INodeIn.SetConnectionHandler to control whether or not pins of custom type can connect.