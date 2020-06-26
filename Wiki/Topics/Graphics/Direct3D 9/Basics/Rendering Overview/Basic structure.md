# Basic structure


![](~/img/Basics2.png "")   



In most situations when you render something you have basically the same patch structure:  

1. some primitives (like the <span class="node">Quad (DX9)</span> ) or meshes with their effects (like the <span class="node">Sphere (EX9.Geometry)</span> and <span class="node">PhongDirectional (EX9.Effect)</span> ) 
1. are placed using the Transformation nodes (like the <span class="node">Translate (Transform)</span> or <span class="node">UniformScale (Transform)</span> ) 
1. grouped together 
1. and rendered to a window.

Working with a 3d scene? You need a [Depthbuffer](TODO INTERNALLINK:rendering-overview#depthbuffer).  

Seeing jagged and ugly edges? Turn on [Antialiasing](TODO INTERNALLINK:rendering-overview#antialiasing).  

Want to set a renderer to fullscreen?  
* move it to the desired monitor  
* change its <span class="pin">Fullscreen Dimensions</span> using the [Inspektor](TODO INTERNALLINK:the-gui#herr-inspektor)  
* press ALT+Enter to toggle it to/from fullscreen  

See the Renderer (EX9)'s helppatch for details.  

Examples in your vvvv\girlpower\ directory:  
* Graphics\DX9\Geometry  
* Graphics\DX9\Shader  

**See also:**  
* [Primitives](TODO INTERNALLINK:geometry#primitives)  
* [Geometries](TODO INTERNALLINK:geometry#primitives)  
* [Built-in effects](TODO INTERNALLINK:shader#built-in-effects)  
* [Transformations](TODO INTERNALLINK:transformation)  




