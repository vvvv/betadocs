---
uid: 4a3a1653-5c09-4102-a148-8f014f3d9a2e
---

# Creating Feedback Loops

![](~/img/FeedbackLoops_ConnectionRefused.png "")   


If vvvv does not allow you to create a connection between two pins that would normally be connectable because they have the same datatype, this is most likely because the link would create a loop in the graph.   

**Creating a loop is not a valid connection!**  



![](~/img/FeedbackLoops_ConnectionAccepted.png "")   


### Solution
Use a <span class="node">FrameDelay (Animation)</span> (or another suitable for your datatype) in the loop to be able to close it. The framedelay is essentially breaking the loop in that its output is not depending on its input of the same frame but simply returns the value the input had in the last frame.  



![](~/img/FeedbackLoops_Understanding2.png "")   


### Understanding
Here we provide two different ways to think about loops in a graph:  

#### Local Varibales  
In order to save the result of a computation in one frame to use it for further calculation in the next you have to use a node called FrameDelay. Essentially by setting its input you write a local variable which you can read from in the next frame by connecting to its output.  

#### Order of Execution  
vvvv does not have an execution order. All things in the graph happen at the same time, once every frame. So every frame of evaluation starts at sinks (Renderers, Writers,..) which first require their inputs to be updated before they can and return their own result. Like this vvvv walks up the graph from each sink until it finds a node that does not have any of its inputs connected. This node can return a result immediately which it "hands over" to nodes connected on its own outputs. Now those nodes can compute their output and so on...without you having to worry about this much.    

While this makes things very easy most of the time, there is one point, where you need to look closer: If you'd patch a loop there would not be a node that can start computing its result since all of the nodes in a loop depend on the result of an upstream node.   

While this sounds like a classical paradox which should lead to crashed computers and blue screens, a solution is quite simple:  At one point in the loop we need to resort to the value of the *last* frame.  

Therefore vvvv prevents you from creating such loops by simply not allowing you to make such connections.   


