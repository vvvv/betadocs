---
uid: 4ae45235-b247-4d0d-8c5b-9d0688f99b3f
---

# Built-in Effects


<a href="http://en.wikipedia.org/wiki/Shading" class="extURL" target="_blank">Wikipedia on Shading</a>  
<a href="http://en.wikipedia.org/wiki/Gouraud_shading" class="extURL" target="_blank">Gouraud</a>  
<a href="http://en.wikipedia.org/wiki/Blinn%E2%80%93Phong_shading_model" class="extURL" target="_blank">Phong</a>  

#### Related nodes
<span class="node">Constant (EX9.Effect)</span>  
<span class="node">FlatPoint (EX9.Effect)</span>  
<span class="node">FlatDirectional (EX9.Effect)</span>  
<span class="node">GouraudPoint (EX9.Effect)</span>  
<span class="node">GouraudDirectional (EX9.Effect)</span>  
<span class="node">PhongPoint (EX9.Effect)</span>  
<span class="node">PhongDirectional (EX9.Effect)</span>  
...and some more  




Effects are the direct3d way to combine vertex- and pixelshaders in one file.   

VVVV ships with a small range of default effects:  

* **Constant**: draws the geometry with a color and/or texture. Looks exactly like the DX9 primitives.  
* **Flat, Gouraud, Phong**: with Point or Directional lighting they implement classic shading algorithms to get simple 3d looks.  

Those effects work for fast prototyping but are really rather dumb and can easily be adapted to use multiple lights and textures, show special shading or whatevvvver, see *Custom Effects* below.  

If you are looking for the Video-Effects for your images/textures/videos, check the [TextureFX nodes](TODO INTERNALLINK:texture#video-effects-TextureFX).   

Examples in your vvvv\girlpower\ directory:  
* Graphics\DX9\Shader\  





# Custom Effects


<a href="http://msdn.microsoft.com/en-us/library/bb173329%28VS.85%29.aspx" class="extURL" target="_blank">MSDN about Effects</a>  

#### Related nodes

<span class="node">Template (EX9.Effect)</span>  


vvvv allows you to write your own pixel- and vertexshaders without using an external tool. Head over to the [effects](TODO INTERNALLINK:effects) section to learn how.   

Examples in your vvvv\girlpower\ directory:  
* Graphics\DX9\Shader\  

**See also:**  
* [Of effects and shaders](TODO INTERNALLINK:tutorial-of-effects-and-shaders)  
* <a href="https://vvvv.org/contributions/1353+1351+2439+1352+7934+2438+1354+1355/1713+2691+2643+2147+1586+1554+3270+4073+3807+1584+2696+1892+3254+1562+1507+1583+1574+1555" class="extURL" target="_blank">Related Contributions</a>  
* [EX9.Effect.File](TODO INTERNALLINK:EX9.Effect.File)  
* [EX9.Effect.Node](TODO INTERNALLINK:EX9.Effect.Node)  
* [EX9.Effect.Template](TODO INTERNALLINK:EX9.Effect.Template)  
* [EX9.HLSL.Introduction](TODO INTERNALLINK:EX9.HLSL.Introduction)  
* [EX9.HLSL.Semantics](TODO INTERNALLINK:EX9.HLSL.Semantics)  
* [EX9.HLSL.Annotations](TODO INTERNALLINK:EX9.HLSL.Annotations)
