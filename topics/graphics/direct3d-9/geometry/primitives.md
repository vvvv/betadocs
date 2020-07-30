---
uid: 3c360048-ceb5-4e96-86d6-5e8ef7ff43e9
---

# Primitives


#### Related nodes
<span class="node">Quad (DX9)</span>  
<span class="node">Segment (DX9)</span>  
<span class="node">Sphere (DX9)</span>  
<span class="node">Rope (DX9)</span>  
...and many more  




Primitives in the 'DX9' category combine a 3d geometry and a drawing effect (ie. shader) in one node. They are always only drawn with constant shading, no lighting.  

These nodes return a 'Layer' which can be directly plugged into the Renderer or a Group.  

Primitives can be colored using <span class="pin">Color</span> and textured using <span class="pin">Texture</span>.  

DX9 nodes internally use the direct3d fixed function pipeline (to whom this may mean something).  

Examples in your vvvv\girlpower\ directory:  
* Graphics\DX9\Geometry  



