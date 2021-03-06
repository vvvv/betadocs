---
uid: 3e4234be-a4b9-49b1-bc17-ba9bf1ab2f54
---

# Change Log - vvvv33beta11
released on 28 07 06  

## general
* Unicode support - you will now be able to render all unicode characters and work with UTF-8 strings  
* you can now personalize vvvvs splash screen or omit it at all. you guess how!  
* the root-patch now only asks for being saved when you first have manually saved it once.  

## bug fixes
* bug in graph fixed. sometimes values were flowing without connection or values were not transmitted on a link  
* Styx (Windows) now finds its .dll  
* no more accessviolation while an effect cannot be compiled  
* ViewFrustumCulling (EX9.Geometry Mesh) now deals with spreads correctly  
* BoundingBox (EX9.Geometry Mesh): fixed memory leak and CenterAll Output  
* Text (EX9.Geometry Mesh) now correctly reports changed status  

## changed nodes
* OSCEncoder (Network) is now spreadable and can encode to bundles  
* OSCDecoder now copes with concatenated OSC messages (even if they are not bundled)  
* IOBox(String) you now can paste UTF8-encoded strings into the iobox and it displays UTF8-encoded strings and control characters (#0..#32 and #127)  
* Length(String) now can deal with UTF8-encoded strings  
* Split(String) now can handle UTF8-encoded strings  
* Text(GDI) now can render UTF8-encoded strings  
* Typospread(Spreads) now can cope with UTF8-encoded strings  
* Ord(String) now can convert hexadecimal strings to numerical values  
* FileStream (DShow9) also now supports Quicktime Alternative >= 1.71  

## new nodes
* GlyphInfo(String) tells if a given character is defined in the chosen font and outputs the width of the character corresponding to the chosen font(size)  
* TextMetrics(String) outputs certain textmetrics of a chosen font