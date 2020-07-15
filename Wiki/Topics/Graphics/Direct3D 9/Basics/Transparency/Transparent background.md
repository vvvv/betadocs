---
uid: cf99781c-e93e-4442-90ff-18a517331eb9
---

# Transparent background


#### Related nodes
<span class="node">DX9Texture (EX9.Texture)</span>  
<span class="node">SetAlpha (Color)</span>  



The image rendered by a Renderer can be retrieved as a texture via the <span class="node">DX9Texture (EX9.Texture)</span>. This is useful if you need to write it to disk, post-process the image (aka [TextureFX](xref:93b2f838-bbd4-423c-81cb-09820d98537d) ) or use it in a feedback-loop.  

In order to render on a transparent background the alpha in <span class="pin">Background Color</span> of the <span class="node">Renderer (DX9)</span> must be <1 and the <span class="pin">Format</span> of the Renderer or the <span class="node">DX9Texture (EX9.Texture)</span> must contain an alpha channel as well. Typically choose A8R8G8B8.  

Examples in your vvvv\girlpower\ directory:  
* Graphics\DX9\Texture\TransparentTexture.v4p  


