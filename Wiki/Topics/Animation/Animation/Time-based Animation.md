---
uid: f597c278-1404-4ecb-bf2f-0f23bb4f2690
---

# Time-based Animation


#### Related nodes
Generators:  
<span class="node">LFO (Animation)</span>  

Filters:  
<span class="node">Damper (Animation)</span>  
<span class="node">Oscillator (Animation)</span>  
<span class="node">Newton (Animation)</span> - accelerates & decelerates  
<span class="node">OneEuroFilter (Animation)</span>  
<span class="node">LinearFilter (Animation)</span>  
<span class="node">Tweener (Animation)</span>  
<span class="node">ADSR (Animation)</span>  
<span class="node">Decay (Animation)</span>  
<span class="node">DeNiro (Animation)</span> - accelerates, drives with constant speed, decelerates (just like a taxi driver)  

...and many more, see the Animation category.  


When there must be a transition between a starting point (A) and a target point (B) and the animation of the value depends only on time, then the nodes from the Animation category do the tweening for you.  

These nodes are building a function curve to animate from A to B and sample this curve as the time goes (independent from the framerate), returning a new value every frame.  

If point B changes during the animation, the node builds a new curve and smoothly animates to the new target.  

If you just want to smoothen (filter) input values, besides <span class="node">Damper (Value)</span> or <span class="node">Newton (Value)</span> there is also <span class="node">OneEuroFilter (Animation)</span> worth checking out.  

**See also:**  
* [Clock Sources](TODO INTERNALLINK:Clock Sources)  
* <a href="https://vvvv.org/contributions/1353+1351+2439+1352+7934+2438+1354+1355/3311+3812+2492" class="extURL" target="_blank">Related Contributions</a>  



