---
uid: 1f0eb4dc-a1fe-4f91-abd7-7cec51fd4d55
---

#  Resource synchronization

Now you have both of your units running happily in parallel. There is an issue.  

If we look at the ConstantInstanced, which is fed by a Dynamic buffer.  

We need to upload our transformations to the buffer. Which is done in 3 stages:  
* Issue a Map Command, indicating we want to write to the resource  
* Upload Data from CPU to GPU  
* Issue a Unmap command, indicating that we are done updating the resource.  

One very important part is that Map command will also instruct the GPU that it's not allowed to use this resource (since we are currently writing on it).  

What it means is that if your GPU's next command is a draw call using that buffer, it will wait until Unmap is called before to proceed.  

This is called a stall. It means your GPU will go idle until upload is done.  

Now please note that this works both ways, if your GPU is currently using the resource for a draw call and you call Map, your CPU will wait for the GPU to instruct that it is done with it before to proceed. This is also a stall, but this time on the CPU side.  

Now since most time we upload resources during update stage, this generally minimizes the risks of having it happening (at the cost of an extra stage).  

Now we have a few nodes which create an exception : Data Retrievers.  

