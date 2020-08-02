---
uid: 46871d51-01e7-4212-b6bc-d44443d2edb0
---

# Change Log - vvvv33beta2
released on 31 01 03  

## general
* added: a whole bunch of help files.  
* changed: default maximum framerate set to 120 to save cpu in trivial patches. default maximum framerate when running in background is 30  
* Alt+F1 on a selected node invokes online help  
* docking - Alt+Drag in Windows to dock them to other windows  
* ctrl-tab cycles through a list of all currently visible windows  
* 'set as root' - will no longer overwrite 'Args.txt' but add to it  
* set as root is now done immediatly, and not only the next time you open vvvv  
* save, save all, delete/close patch behaviour more secure & logical  
* inspektor will no longer write values of previously seleceted nodes to a newly selected node  
* Audio nodes will not crash anymore on a system without any audio input  

## new nodes
* AudioInput (DirectShow8)  
* RMS (DirectShow8) - get the root mean value of an incoming audio signal  

* FFT (DirectShow8) - get a spread with the frequencies of a audio signal  
* ScopeSpread (DirectShow8) - get a spread with the waveform of an audio signal  
* URLSource (DirectShow8) (experimental - havent found an url with a file to open) - the node just encapsulates the DirectShow node with the same name)  
* TSHR200 RFID GIS Tag reader support  
* Length (String)  
* SetSlice (String)  
* Split (String)  
* Shift (String)  
* Cons (String)  
* QueueSpread (String)  
* RingBuffer (String)  
* S+H (String)  
* EQ (String)  
* ClientID, ClientSetup, ServerSetup (VVVV)  
* MainLoop (VVVV) - allows to set maximum frame rate in foreground/background mode.  
* MidiController (Devices, Relative) for use with devices like the Native Instruments 4control or DOEPFERs pocket dial  
* Blend (Color)  

## changed nodes
* Pad (String) will now clip input string if input is larger then specified size  
* renamed output of Cons (Spreads) node to "output" (was "remainder" which didnt make sense)  
* added proxy + proxyport to HTTP (Get)  
* added OnSuccess bang output to HTTP (Get)  
* added Hex mode to Byte (String)  
* S+H will sample the input value once during initialisation; another bug removed  
* FormatValue (String) has Leading Zeroes pin  
* TMRegExpNode will not throw an assertion if matchcount is inconsistent  
* ioboxes got a new pin SliceCount Mode.  
* directshow nodes will be much quieter in the log  
* font for ttyrenderer is now "Lucida Console"  
* changing the spreadcount will change FPinIsChanged and FObserverChanged in ValuePin, ColorPin, StringPin, EnumPin  
* Shortcuts for making screenshots of the active window are now: <span class="keyseq"><kbd>Ctrl</kbd><kbd>F10</kbd></span> (without border) and <span class="keyseq"><kbd>Ctrl</kbd><kbd>F9</kbd></span> (with border)  
* GDI textures - connect them directly to the GDIRenderer which is the source for the texture  
       
## fixed nodes
* FormatValue will work with arbitrary amounts  
* shortcut for toggling updateview (Alt+U) now works  
* cursor might have been invisible when returning to vvvv from another program  

* tooltips will now for sure be hidden when switching to locked mode  
* ioboxes will now hide in locked mode if set to "hidden when locked"  
* 'show root' will show a loaded root with its saved dimensions  
* boygrouping for network setups will now work  
* directshow nodes will now automatically re-initialize when connection is changed  
* crash with AudioRecordSelector  
* mouse (system global) will now allow multible instances on win98 machines.  
* iobox (color) - now works in all modes  
* improved stability of video texture when selecting between various texture sizes  
* netsend/receive basically working but mostly still buggy. sory.  
* String nodes are now much faster with constant inputs  
* improved Renderer (DX8): can now switch to various full screen modes, in windowed mode now it's possible to set the backbuffer size manually, multiple renderers work independently from each other