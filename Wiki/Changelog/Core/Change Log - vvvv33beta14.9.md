---
uid: a089cbec-adf1-4826-b303-2fd5a767f97c
---

# Change Log - vvvv33beta14.9
released on 26 03 08  

## general
* undo of a subset of slices within a bigger spread now works as expected  
* all nodes now have a hidden pin that returns their ID in the patch  
* copy & paste behaviour with more options, better defaults and fixed linkpoints offset  
* new commandline switch: /dda X (where X is the device ID of the device a renderer will go fullscreen on startup) only needed if having troubles going fullscreen on any device other than the primary (which would be 0)  

## fixed nodes
* Renderer (DX9): no more cursor and gdi-flicker in fullscreen  
* Mouse (System Window): middle and right mousebuttons now always release on mouseup  
* DX9Texture (EX9.Texture): now works on multiple devices  
* Pipet (EX9.Texture): now works with more texture formats  
* Fog (EX9.Renderstate): should work more reliable  
* WavePlayer (DShow9): greatly enhanced  
* Queue (Spreads), RingBuffer (Spreads): no more division by zero if Insert is nil  
* Select (MySQL): can now deal with nil inputs  
* OSCDecoder (Network): now evaluates for sure   


## changed nodes
* Sequencer (Animation): now has a CycleCount output  
* Sift (Value): now has a pin called *Epsilon* to sift with a given tolerance  
* ConvexHull (2D): now spreadable via a new *BinSize* pin  
* Memory (Debug EX9): now returns output in megabytes instead of bytes  
* Dir (File): now returns the filecount per input directory  
* Processes (Windows) now has a pin called *Update* which needs to be banged in order to update the process-list  
* FileStream (DShow9) finally plays <a href="http://avisynth.org" class="extURL" target="_blank">avisynth</a> scripts  
* Self (VVVV): added pin *ID in ParentPatch*  
* Renderer (Flash): added pins *DoSeek* and *SeekFrame*  
* Effects now take arrays of values and colors per slice  
* Cons (Spreads): should now be faster on larger spreads  
* SetPatch (VVVV) , GetPatch (VVVV), PatchAlias (VVVV), PatchAlias (VVVV Name) are spreadable now  

## new nodes
* SourceBuffer (DShow9): writes your favorite values to a multichannel soundcard  
* SharedMemory (Windows): can access a shared memory file  
* SharedMemory (EX9.Texture): creates a texture from a shared memory file  
* SharedMemory (DShow9 TransformInPlace): passes video through and writes mediasamples to a shared memory file  
* VideoOut (DShow9 SharedMemory): writes mediasamples to a shared memory file  
* SetProcessAffinityMask (Windows): Assigns a process to specific processors  
* NodeList (VVVV) outputs a list of all vvvv nodes  

## new modules
* B-Spline (3D Wryly) with which you can twist a B-Spline  