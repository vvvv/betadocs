---
uid: 2ffcdd83-93f8-4c2b-8502-2a0e165160f4
---

# Change Log - vvvv50beta38.1
released on 13 12 18  

## VVVV
* pressing ALT+CTRL+rightclick on a node that also has a window, now resets the windows position to the mouse cursor position  

## VL
* fixed json arrays not being converted from b37 to b38   
* fixed regression that pin editors and resetting of pins didn't work anymore   
* fixed regression that default values on pins didn't work when interacting with them   
* RegisterServices methods can also be written in C# now. Moved registration of VL.CoreLib serializers into it.  
* Static entry points (which register serializers) will be called on startup before any UI loads  
* fixed race condition in IVLFactory implementation (caused random null pointer when serializing)  
* fixed fallback editor being used for a short time when creating a new pad  
* fixed bug in CLR type importer not being able to map generic CLR types to VL types  
* fixed non-primitive default values not being emitted  
* fixed handling of null as a default value for a parameter  
* fixed crash when implementing interface in patch  
* added the type to deserialize to the ISerializer interface so we don't have to rely on a default value being present  
* fixed candidate lookup for anonymous types when hot swapping a delegate  

### changed nodes
* Executor: now has "Working Directory" input  

### new nodes
* added swizzle nodes  
* added Radix node  