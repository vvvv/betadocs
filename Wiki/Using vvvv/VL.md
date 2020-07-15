---
uid: 89e664e5-1274-4966-a7cd-82255eea4483
---

# VL

VL is a new visual programming language supported in vvvv that combines dataflow paradigms with features from object-oriented programming. It builds directly to the <a href="https://en.wikipedia.org/wiki/Common_Intermediate_Language" class="extURL" target="_blank">.NET Intermediate Language</a> and can also consume .NET libraries.  

vvvv and vl work together in harmony. Whenever you're stuck in vvvv with expressing a certain problem, VL can most likely help out. This greatly reduces the number of cases when you'll have to resort to C# as a fallback solution.  


# Features

![](~/img/DataType.PNG "")  
*Define a Particle with properties (position, velocity, radius) and a create (white), update (gray) and hittest (blue) operation*  

### Datatypes
Besides primitive data types like String, Value, Color,... VL allows you to patch your own complex data-types with custom behavior and lets you create and manage dynamic instances of them.  



![](~/img/loops.png "")  
*Iterate over the Particles in a spread and keep those whose lifetime is < 100*   

### Loop regions
In vvvv all looping is handled via automatic spreading inside the nodes. VL hands this power to the patcher which opens up a whole new world of possibilities.  



![](~/img/generics2.png "")   
*Patch operations without specifiying a datatype for its inputs or outputs*   

### Generics
Generic programming, the implementation of operations irrespective of the concrete data type used at runtime is widely supported in modern programming languages. In VL, however, it is the default, which is very useful for creating libraries that work for any data type.  



![](~/img/asynctask.png "")  
*Trigger the execution of a webrequest in an async region to not block the mainloop*   


### Async Regions
Sometimes parts of a program take longer to compute but should not block the mainloop. For those scenarios VL has async regions. Anything inside them gets computed on a background-thread and reports its result when finished.  



![](~/img/delegates3.png "")  
*Decide at runtime whether to order by time or id*   

### Delegates
In VL, operations can be passed over links. Like this a patch can invoke an operation at runtime that has not been explicitly specified before. A powerful pattern in modern programming that makes generic and modular patching a breeze.  



![](~/img/observable3.png "")  
*Handle midi-events as they occur and only send controller messages to the midi-output (without touching the mainloop)*  

### Observables
VL embraces observables to do event handling. This approach works well together with the dataflow paradigm and is very flexible.  


# Getting Started


VL is included with vvvv since version beta35. Here is what should get you going:  
* [Download](https://vvvv.org/downloads) vvvv + addonpack  
* Check the demo patches in the \girlpower\VL directory  
* <a href="https://discourse.vvvv.org/c/tutorials" class="extURL" target="_blank">Video Tutorials</a>  
* [Quick Reference](xref:2879ae37-9e84-42ee-8e2e-8444d274bb6b)  
* Check the <a href="https://vvvv.org/blog/23" class="extURL blog" target="_blank">devvvv blog</a> for most recent updates on VL  
* <a href="http://thegraybook.vvvv.org" class="extURL" target="_blank">The Gray Book</a> (in the making)  
* <a href="https://discourse.vvvv.org/tags/vl" class="extURL" target="_blank">VL topics in the forum</a>  


# VL in use


A couple of nodes shipping with the vvvv library are already relying on vl internally. Here is an incomplete list, just to give you an idea:  
* Editing Framework (Cameras, Point- and BezierEditors)  
* Arduino/Firmata nodes  
* TUIO encoder and decoder nodes  
* Midi File Reader  
