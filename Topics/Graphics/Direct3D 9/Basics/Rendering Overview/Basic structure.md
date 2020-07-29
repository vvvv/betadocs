---
uid: 555a9b26-208f-43ef-a7dc-f5893200df65
---

# Basic structure


![](~/img/Basics2.png "")   



In most situations when you render something you have basically the same patch structure:  

1. some primitives (like the <span class="node">Quad (DX9)</span> ) or meshes with their effects (like the <span class="node">Sphere (EX9.Geometry)</span> and <span class="node">PhongDirectional (EX9.Effect)</span> ) 
1. are placed using the Transformation nodes (like the <span class="node">Translate (Transform)</span> or <span class="node">UniformScale (Transform)</span> ) 
1. grouped together 
1. and rendered to a window.

Working with a 3d scene? You need a [Depthbuffer](xref:59a77510-fda1-499a-9686-461a2ab446c9).  

Seeing jagged and ugly edges? Turn on [Antialiasing](xref:6d879681-cfa1-4021-a138-e824327b1a8a).  

Want to set a renderer to fullscreen?  
* move it to the desired monitor  
* change its <span class="pin">Fullscreen Dimensions</span> using the [Inspektor](xref:9666611a-6f15-4b33-8300-69f56d9ec7d4)  
* press <kbd>ALT+Enter</kbd> to toggle it to/from fullscreen  

See the Renderer (EX9)'s helppatch for details.  

Examples in your vvvv\girlpower\ directory:  
* Graphics\DX9\Geometry  
* Graphics\DX9\Shader  

**See also:**  
* [Primitives](xref:3c360048-ceb5-4e96-86d6-5e8ef7ff43e9)  
* [Primitives](xref:3c360048-ceb5-4e96-86d6-5e8ef7ff43e9)  
* [Built-in effects](xref:4ae45235-b247-4d0d-8c5b-9d0688f99b3f#built-in-effects)  
* [Transformations](xref:733b862c-97e1-4309-a023-3af1ede604e5)  




