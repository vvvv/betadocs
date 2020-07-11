---
uid: f121aba1-f3d8-42ab-8ce8-f5ba984494cd
---

#  What is a Data retriever?

Sometimes let's say we need to access a GPU resource and bring it back to our CPU (Simple Readback).  

What we need to do is:  
* Create a resource that we can read in CPU (this is called a staging resource)  
* Copy our GPU resource to the staging resource.  
* Indicate to our GPU that we are gonna read that resource.  

This is also done, using Map, but this time we tells that we want to read.  

What now happens is:  
* Since we tell we want to read, the GPU but execute ALL remaining commands (you flush the gpu).  
* Your CPU needs to wait for the GPU to execute (so your CPU will go idle until this is done).  
* You copy your data back, then do some other processing.  
* Since you just emptied the command buffer, your GPU will do nothing until it receives new commands.  

Let's take this simple (but oh so common) example:  

![](~/img/02_Early_Render_2013.10.18-14.47.54.png "")   

Now what happens in there.  

We have an Info node. To output it's data, the node needs to have all the above fully evaluated (which is handled by vvvv graph), but also fully updated and rendered. And we are still at evaluation stage, since we need to output data as output pins.  

So here we create what is called an "Early Render"  

Basically our info node (during evaluate), will instruct the DX11 pipeline that it needs this resource ready.   

Our vvvv pipeline will call Update/Render using Info as a starting point. So all of the above will be processed. Since we also need the runtime to fully complete the draw calls, our Info node (which doesn't do much), will actually under the hood provoke quite a big chain of actions.  

By doing this, and since our node still need to wait for that data, we lose the benefit of having our CPU and GPU work concurrently.  

That's why your node will suddenly appear to eat a lot of CPU when you run in Debug Mode, which is misleading since thispart would have been rendered anyway.  

Please of course note that the dx11 rendering knows that this part has already been rendered, so when you reach update/render it will not process it a second time. This means that performance loss can be fairly minimal or very bad (it can really depend on lot of factors). But mostly it also makes rendering path unpredictable (which removes opportunities for internal optimization).  

So to make it simple, reading back resources has a lot of implications, it needs to be handled with care. Please note in some cases this is needed and not avoidable.  

In the case of Info, this should never be needed anymore in dx11 (except for debug purposes).  
* TextureFX will inherit resource size.  
* You have access to GetDimensions in hlsl to query resource size.  
* Semantics are provided to shader if you need render target size.  

In some cases, reading back data for CPU usage is unavoidable (send some stream compaction results via network for example, export model/texture).  

Please note that retrieving average brightness of a texture to connect to a Damper is NOT a use case ;)  

If data is not needed within the same frame, write a node that waits for presentation stage, and Map your resource after that (since your pipeline will be fully executed, so you will minimize the chance of a big fat stall).  