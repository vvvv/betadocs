#  Overview

VVVV Pipeline in DirectX 11 is somehow similar to the one in DirectX9 (with some differences).  

From the time that your patch is evaluated to the time you finally have something on the screen, a lot of different processing (happening magically under the hood) happens.  

This processing is divided in different stages:  
* Evaluate : Each node is evaluated and process it's own logic.  
* Update : This is called for every node that owns/process a DirectX resource (please note that there are some optimizations behind, but we'll speak about that in another topic). Update stage makes sure that any resource gets updated properly to your GPU prior to issue rendering commands.  
* Render : This is when you really issue render commands.  
* Present : For any render window which is visible, we send a Present command (which basically means show the result on the screen).  

So now GPU pipeline is Asynchronous, let's see what it means using this simple example:  

![](~/img/01_Sync_Pipeline_2013.10.18-13.39.46.png "")   

Now let's consider for a minute that we have a synchronous pipeline:  

Update stage uploads Quad/Sphere and DynamicBuffer to your GPU (if not already).  

Now the rendering goes to constant, which issue a draw command. Since we imagine our pipeline as synchronous that means (CPU wise)  
- Set Shader Stages  
- Send Draw command for Quad.  
- Wait for Draw Command to be completed.  
- Set shader stages for sphere  
- Send Draw Command for Sphere 0  
- Wait   
- Send Draw Command for Sphere 1  
....  

our GPU would work like that:  
- Wait  
- Receive command for Quad  
- Process quad  
- Notify that you're done  
- Wait for next command  
....  

As you can clearly see this would be totally inefficient, both of your processing units would permanently wait for each other. This is called idle time.  

So instead pipeline works this way, calls to the Pipeline are asynchronous, which means when you send a graphics command, it is not processed right away. Instead this is stored in a command buffer. Your GPU will then consume commands from this buffer when it feels it needs too.  

What it now means, if we take our previous example, that your CPU is immediately free to make more work once commands are sent. And your GPU gets commands and process them at some point.  

Now that means your GPU might effectively draw you Quad while your CPU is issuing draw calls for Sphere number 5.  

So an important aspect is: you don't know when the GPU is processing commands (please note that order is of course preserved). And technically you don't really want to know, letting both units do their job is much easier.  

There are a few ways to instruct your GPU to immediately process commands in his buffer:  
* When you call present (since you ask for result on the screen we need our graphics card to complete the job).  
* When you issue a Flush command (basically never do that unless you know what you do, this is useful in a few cases, but mostly for cleanup).  
* When you Map a resource for read (more on that later).  

