---
uid: a60c6d21-4033-4d10-81af-8fa4f25b63b1
---

# Change Log - vvvv33beta15.1
released on 03 04 08  

## general
* dtd updated to be be valid for patches with hidden pins  
* fixed some random evaluation bugs (partly related to s and r nodes)  
* fixed a problem with singletons (nodes which internally only exist once, even when they display in more than one patch)  

## changed nodes
* SetMatrix (EX9.Transform) got new pin called *Update*  
* + (String), + (String Spectral), Separate (String) are more flexible in their intersperse modes.  
* S+H nodes got an additional "Set on Create" pin  
* Togedge (Animation), Change (Animation) got an additional pin "Bang On Create"  
* XPath (XML) is fully spreadable now. it should also be faster on new queries on unchanged XML documents.  

## fixed nodes
* Pipet (EX9.Texture) now takes background-color of connected renderer including alpha and fakes alpha for all X... texture formats  
* Mouse (System Global) corrected subtypes of X and Y outputs  
* Writer (File) couldn't write a second time  
* Effect (EX9.Effect): fixed error with arrays of colorpins  
* S+H nodes bug fix (was sampling input when it was empty in the frame before)  
* Waveplayer (DShow9): Sync, DoSeek now spreadable,no crash if driver is changed while playing  
* Counter (Animation) fixed another time. outputted NAN in very special cases  

## help
* DeNiro (Animation) got a help file  