# Frame-based Animation

#### Related nodes
to built up your loops:  
<span class="node">FrameDelay (Value)</span>  

to accumulate values over time or get changes between frames:  
<span class="node">Integrate (Differential)</span>  
<span class="node">FrameVelocity (Animation)</span>  
<span class="node">FrameDifference (Animation)</span>  

to measure time itself:  
<span class="node">StopWatch (Value)</span>  

nodes that are frame-based implementations of some algorithm:  
<span class="node">ADSR (Value Framebased)</span>  
<span class="node">Spray (Animation)</span>  
<span class="node">Wanderer (Animation 2d)</span>  
<span class="node">Wanderer (Animation 3d)</span>  



Scenario: an object shall react to events by applying forces.   
There are different famous examples of this way of doing animations:  
* BOIDS  
* Physics engines, like <a href="https://vvvv.org/contribution/box2d" class="extURL contribution" target="_blank">Box2D</a> or Bullet (included in <a href="https://vvvv.org/contribution/directx11-nodes" class="extURL contribution" target="_blank">DX11</a>).  

But you also can do your own frame-based animation, simply by patching.  

![](~/img/FeedbackLoops_Understanding2_0.png "")  

The basic idea here is that the current value of the animation is simply calculated based upon the value of the last frame and tweaked a bit in a certain way. See more about [Loops](TODO INTERNALLINK:patching-concepts#loops).  

When doing this naively, higher frame rates will result in faster animations. To avoid that, here is a simple trick:   

* measure how much time has passed between the last frame and the current frame. A combination of <span class="node">Stopwatch (Animation)</span> and <span class="node"> FrameDifference (Animation)</span> can help you out.  
* scale your velocity and acceleration by this amount  

As a result your animation will be framerate independent.  

**See also:**  
* <a href="https://vvvv.org/contributions/1353+1351+2439+1352+7934+2438+1354+1355/3402+3400+2492+7216" class="extURL" target="_blank">Related Contributions</a>  



