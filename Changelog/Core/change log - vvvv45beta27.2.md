---
uid: 07c03ebe-ee34-427e-bf84-871e27a37a61
---

# change log - vvvv45beta27.2
released on 08 05 12  

## general
* when using modules as QuickNodes they no longer show their patch  
* DoQuit (VVVV) can now take an ExitCode which vvvv returns on the commandline  
* fixed: <a href="https://discourse.vvvv.org/t/patch-xml-attributes-rearranged" class="extURL forum" target="_blank">patch-xml-attributes-rearranged</a> which will come handy for version-controlling patches  
* re-introduced codecompletion for .fx (can still be removed by deleting \lib\hlsl.fnr)  
* NodeBrowser  
  * fixed redraw-errors in categoryview and modules drag-dropped on a patch no longer open as patch  
  * when opened in standalone mode (ctrl+n) it only showed 20 lines  
* fixed some pin-connection-troubles that allowed double-links or failed to disconnect links in some cases  
* fixed nodelist.xml: native nodes were missing in 27.1  
* renaming an iobox shouldn't mess up links in other patches anylonger.  
* small debug mode fix: [/forum-alpha/a27.2-debug-mode-bug](https://vvvv.org/forum-alpha/a27.2-debug-mode-bug)  
* bug fixes in the core concerning the information if a pin has changed.  

## fixed nodes
* Sort (String) bug as reported here: <a href="https://discourse.vvvv.org/t/sort-(string)-outputs-only-text" class="extURL forum" target="_blank">sort-(string)-outputs-only-text</a>  
* VertexBuffer (Join) bug as reported here: <a href="https://discourse.vvvv.org/t/vertex-buffer-bug-or-not-bug" class="extURL forum" target="_blank">vertex-buffer-bug-or-not-bug</a>  
* GetSlice returned not empty output bin size when fed with nil. See <a href="https://discourse.vvvv.org/t/posible-bug-in-getslice" class="extURL forum" target="_blank">posible-bug-in-getslice</a>  
* Timeliner (Animation) now imports midi-files correctly and saves keyframes moved via states, as reported here: <a href="https://discourse.vvvv.org/t/timeliner-saving-issues" class="extURL forum" target="_blank">timeliner-saving-issues</a>  
* Renderer (GDI) validates its view-matrix correctly again  
* Styx (Windows) node didn't clean up properly after being destroyed  
* AsString (SVG) outputs the strings according to the input slices now