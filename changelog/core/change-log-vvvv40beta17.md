---
uid: 7594d010-7893-4237-87d1-e2084e8e9c66
---

# Change Log - vvvv40beta17
release on 16 07 08  

## general
* some Undo bug removed  
* ID pins don't return NIL anymore  
* better Boygroup debugging tools (check the Boygroup nodes)  

* boygroup server now takes optional broadcast IP on the commandline after the /server switch (else broadcasts on default network adapter)  
* convverter (diff.xml) can convert nodes (and patches) with inputs and outputs having the same name  
* you can now find the nodelist.xml file in \bin which holds a specification of all nodes in the current release (still missing: plugins, modules, freeframes, effects)  
* new commandline argument: "/shutup" will disable all shortcuts (but Alt-F4) and won't let patches nor inspectors show up  
* vvvv now supports VST effects and instruments within sound graphs  

## plugin interface
* plugins may now implement IDisposable to be notified when the plugins node is being destroyed  
* plugins may now use the Log() function to write directly to vvvvs console, ie. Renderer (TTY) at any time  
* plugin-pins have a new property: IsConnected  

## new nodes
* Copy (String) returns substrings containing Count characters starting at Index  
* DMX (Devices ecue Texture) sends textures to ecue devices according to an ecue-patch-file  
* DMX (Devices ecue Butler) sends DMX values to ecue Butler devices  
* eNet (Devices ecue Info) shows ecue devices that are visible in the local network  

## changed nodes
* WavePlayer (DShow9) can now output to multichannel soundcards  
* Writer (EX9.Texture) now creates a specified directory if it doesn't exist.  
* DoQuit (VVVV) now has a QuerySave input  
* UDP (Network Server) now has a BufferSize input  
* Boygroup (Server) now has a MaxUDPSize input  
* VideoIn (DShow9) now has TriggerMode and Trigger inputs  
* Attractor nodes throughput Input to Output when no attractor is specified  
* Switch (Node) should be much faster  

## fixed nodes
* OSCDecoder (Network) fixed OnReceive output and fix with nil inputs  
* SharedMemory (DShow9 TransformInPlace): now accepts more videosubtypes and no longer crashes if reader of memorylocation was there first  
* VideoOut (DShow9 SharedMemory) no longer crashes if reader of memorylocation was there first  
* Homography (Transform 2d) and GaussJordan (Value): memory leak in equation solver  
* Intersect nodes: don't report a false intersection anymore, if no inverse of the world matrix exists  
* VideoTexture (EX9.Texture VMR9 YUVMixing) no longer flickers  