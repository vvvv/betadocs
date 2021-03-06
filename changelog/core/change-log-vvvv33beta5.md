---
uid: a2b690c4-c43d-40fb-8b2a-e79bfb9712c7
---

# Change Log - vvvv33beta5
released on 29 08 03  

## general
* improved boygrouping pervvormance and rendering speed -  if boygrouping nodes need each other they are boygrouped together  
* converted to directX9 due to better performance of video and gdi textures.  converted categories DX8 to DX9, Textures to Textures9 and DShow8 to DShow9  
* when loading patches saved with older versions than beta5 conversion will be done according to difff.xml  
* undo should work pretty well. just note that some few operations like resetting/boygrouping the node are internally split into two actions so that you have to undo twice to get your node back  
* improved speed of IOBoxes. they aren't evaluated if hidden and in input mode  

## gui
* added: ShortCut to 'Rescan for Modules' (Ctrl+M)  
* changed: in the autocomplete nodelist start with a '.' to get patches from the current patchs directory  
* new: shortrightclick a valuepin to enter a constant  
* fixed: alt+rightclick for string- and enumpins  

## nodes
* new: AND (Boolean Spectral), AND (Boolean), NOT (Boolean), OR (Boolean Spectral), OR (Boolean), XOR(Boolean)  
* new: * (Color), InputMorph (Color), S+H (Color), Select (Color)  
* new: CPULoad (Debug), Memory (DX9)  
* new: Dial (Devices Custom), MidiShortOutput (Devices)  
* new: VideoIn (DShow9), VideoOut (DShow9), VideoTexture (Textures9 DShow)  
* new: RSFog (DX9), Sphere (DX9)  
* new: Renderer (Flash) with output to GDITexture and input/output of flash-variables  
* new: IP (Network), Ping (Network)  
* new: Switch (Node Input)  
* new: GetSlice (Node) (only for transformations yet)  
* new: * (Quaternion), AxisAngle (Quaternion Get Vector), AxisAngle (Quaternion Get), AxisAngle (Quaternion Set Vector), AxisAngle (Quaternion Set), Euler (Quaternion Set Vector), Euler (Quaternion Set),  Join (Quaternion), Rotate (Quaternion Point Vector),  Rotate (Quaternion Point),  Rotate (Quaternion Vector), Slerp (Quaternion), Split (Quaternion)     
* new: CountIndices (Spreads)  
* new: * (String), Ord (String), Select (String), Sift (String), Substitute (String), Tokenizer (String)  
* new: ApplyTransform (Vector), ArbitraryPoint (Vector), Rotate (Quaternion), Rotate (QuaternionVector)  
* new: Self (VVVV) reports some info about the patch it is placed in  
* new: Beep (Windows), MessageBeep (Windows)  
* added: Text (GDI) got pins for writing bold, italic and antialiased text  
* added: Outlet FormerIndex to Sort (Spreads)  
* added: reworked FileStream (DShow9) now has VideoOutput and many more  
* added: Cursor (System) has pins to set mouse coordinates and fire clicks  

* added: GDI Output to Renderer (HTTP) and Renderer (TTY)  
* changed: IOBox (String) accepts dropped files  
* changed: spreading a Triangle (dx9 Indexed) spreads the whole geometry  
* changed: IOBox (Node) has binsize pin to group slices (only for transformations yet)  
* changed: spectral nodes better (bin size instead of bin count; -1 means operate on whole spread. spreadable)  
* changed: gditextur faster  
* changed: DX9 nodes have texture projection mode (check out with a Sphere (DX9))  
* fixed: Mainloop is set back to defaults, when the last instance is deleted  
* fixed: I (Spreads): min, max can be negative, some unlikely bugs fixed  
* fixed: gdi render in background   
* fixed: GDITexture, DX9Texture, VideoTexture spreadable via texture transformation  
* fixed: performance of filetexture recovered, first-slice-is-white bug removed  
* fixed: bug in Queue, RingBuffer, Levin   
* fixed: ArbitraryPoint 10000 slices bug  

## modules:
* Wait (Animation).v4p, KeysUpDown (Animation).v4p, Delay (Animation).v4p  
* Within (2d).v4p   
* Damper (Color).v4p, Resample (Color).v4p, SetSlice (Color).v4p, Shift (Color).v4p, Tint (Color Spreads)  
* Normalize (3d).v4p  
* PerfMeter (Degug).v4p  
* Line (DX9).v4p, Torus (DX9).v4p, LineAlongSpread (DX9 3D).v4p  
* ReplaceEmpty (String).v4p, Reverse (String Spreads).v4p  
* MidiControllerOut (Devices).v4p,  TouchFrame (Devices Interact442a).v4p, DMX4all (Devices DMX).v4p  
* Bit (Value).v4p, ReplaceEmpty (Value).v4p, Within(Value).v4p 