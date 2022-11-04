---
uid: "contribution/stencil-mask"
uid-meta: "contribution/stencil-mask-meta"
comments: 
 items: 
  - uid: "233393"
uid-files: "contribution/stencil-mask-files"
title: "Stencil Mask"
image: "Mask.png"
contribution: "true"
---

Demo/helper modules for using the stencil buffer in DX11.


Contains 2 modules: <span class="node">StencilMask (DX11.RenderState Write)</span>, & <span class="node">StencilMask (DX11.RenderState Read)</span>

You can use 8 bits of the depth-buffer as a stencil buffer.  With the Write module we set each bit individually to render 8 independent masks for free (or at slightly-reduced-but-still-quite-ok depth accuracy).

Using the Read module you can limit a shader to only drawing the pixels flagged by any of your mask(s)

You can set all of this in your shader also, but can be handy to not have to modify everything.

Edit: Have changed these to be renderstate only, as <span class="node">StencilReference (DX11.Layer)</span> had some issues and is being depreciated.

