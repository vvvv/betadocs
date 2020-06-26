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



