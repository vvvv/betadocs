---
uid: cfc19801-b2d5-438f-a7f6-0b40e128a236
---

# Introduction


vvvv offers different approaches to animate objects in *interactive*environments.   

In many cases, it's not enough to just place static keyframes on a timeline and let the playhead do the job. The animation may need to react to actions or events coming from sensors, networks, input devices or beat-detectors. So in these cases **the direction of movement needs to change spontaneously** and you often want the transition to the new movement to occur as smoothly as possible. Time- and frame-based approaches can do this trick.  

Still, often you also want to timeline some behavior and even [combine](xref:0cc9f485-467f-41ef-8239-749baae656f4) the different techniques.  


 

So here are the three basic approaches:  

* [Time-based Animation](xref:f03b2df4-e4b6-45c4-a48e-ac50b7b810b4)  
* [Frame-based Animation](xref:46a08b79-6346-4803-8bd0-d6666570b5c8)  
* [Timeline](xref:0f6c2067-f70b-4d38-a079-925b41727b60)  

  


**Time-based** vs. **frame-based** approaches:  

*Time-based:*  
* most time-based filters are parameterized in a way that they **animate towards a target point** within a specified certain time. The target can be changed at any point in time.  
* the animation's speed is independent of the framerate.  

*Frame-based:*  
* typically you think about **events and reaction to those events at the current moment**, not so much about reaching a target in the future.  
* the main idea is to change the value each frame just a bit  
* the animation's speed depends on the framerate and extra care should be taken to avoid it.  

Interested in particle systems?  
* [Particles](xref:05abefd4-4eb6-4b46-8b39-b17105a64aff)  



