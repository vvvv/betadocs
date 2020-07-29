---
uid: 59a77510-fda1-499a-9686-461a2ab446c9
---

# Depthbuffer


#### Related nodes
<span class="node">Renderer (EX9)</span>  
<span class="node">ZWriteEnable (EX9.RenderState)</span>  
<span class="node">AlphaTest (EX9.Renderstate)</span>  
<span class="node">Cull (EX9.Renderstate)</span>  

![](~/img/Basics-Depthbuffer2.png "")   



A Depthbuffer stores the depth information of the scene, ie. a single z-value per pixel.  

If depth buffering is off (which is the default) objects (and their faces) are just drawn in the order of their priority and their slice index - which looks weird as soon as they are seen in the wrong order.   

Turn on depth buffering by selecting the <span class="node">Renderer (EX9)</span> in an [Inspektor](xref:9666611a-6f15-4b33-8300-69f56d9ec7d4). There you'll see a "Windowed Depthbuffer" and a "Fullscreen Depthbuffer" pin. Change their default "None" values to D16, D24 (or similar, where 16 or 24 denote the number of bits available for the depth buffer). Typically choose D24X8.  

The classic name for drawing without the depth-buffer is painters algorithm: start with the things in the background and then paint all things after another on top of it.  

Using the depthbuffer enables a test which is done for each pixel drawn: if a pixel nearer to the camera was already drawn, the new pixel gets rejected. Or to put it the other way round: If the current object to be drawn is nearer to the camera than the stuff already drawn, the object is just drawn on top of the existing color buffer.  

**See also:**  
* [Transparency and Depthbuffer](xref:2f516214-4f5a-4d2c-af84-2a3dc96dc0c4)  



