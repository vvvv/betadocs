# Introduction


vvvv offers different approaches to animate objects in *interactive*environments.   

In many cases, it's not enough to just place static keyframes on a timeline and let the playhead do the job. The animation may need to react to actions or events coming from sensors, networks, input devices or beat-detectors. So in these cases **the direction of movement needs to change spontaneously** and you often want the transition to the new movement to occur as smoothly as possible. Time- and frame-based approaches can do this trick.  

Still, often you also want to timeline some behavior and even [combine](TODO INTERNALLINK:animation#mixed-approaches) the different techniques.  


 

So here are the three basic approaches:  

* [Time-based Animation](TODO INTERNALLINK:animation#timebased-animation)  
* [Frame-based Animation](TODO INTERNALLINK:animation#framebased-animation)  
* [Timeline](TODO INTERNALLINK:animation#timeline)  

  


**Time-based** vs. **frame-based** approaches:  

*Time-based:*  
* most time-based filters are parameterized in a way that they **animate towards a target point** within a specified certain time. The target can be changed at any point in time.  
* the animation's speed is independent of the framerate.  

*Frame-based:*  
* typically you think about **events and reaction to those events at the current moment**, not so much about reaching a target in the future.  
* the main idea is to change the value each frame just a bit  
* the animation's speed depends on the framerate and extra care should be taken to avoid it.  

Interested in particle systems?  
* [Particles](TODO INTERNALLINK:Particles)  



