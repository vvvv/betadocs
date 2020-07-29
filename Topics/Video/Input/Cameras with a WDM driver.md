---
uid: 2ce3c55f-42d9-4e4c-8f44-cd4942e7c405
---

# Cameras with a WDM driver

#### Related nodes
<span class="node">VideoIn (DShow9)</span>  
<span class="node">VideoIn (EX9.Texture)</span>  

<span class="node">VideoTexture (EX9.Texture VMR9)</span>  
<span class="node">VideoTexture (EX9.Texture VMR9 YUVMixingMode)</span>  



Standard cameras (those with a WDM driver) can be simply accessed via the the <span class="pin">Driver</span> pin of the <span class="node">VideoIn (DShow9)</span>.  

Use the <span class="node">VideoTexture (EX9.Texture VMR9)</span> connected to the VideoIn's  <span class="pin">Video</span> output pin to retrieve the video texture which can be:  
* processed by the [TextureFX](xref:93b2f838-bbd4-423c-81cb-09820d98537d),  
* analyzed by the <a href="https://vvvv.org/contribution/vvvv.packs.image" class="extURL contribution" target="_blank">Image Pack</a>,  
* applied to a 3d object (like a <span class="node">Quad (DX9)</span> ) and rendered.  

Examples in your vvvv\girlpower\ directory:  
* Video  

**See also:**  
* [List of Cameras](xref:02abbea9-3a49-401d-bd74-aa89704b87b0#cameras)  


