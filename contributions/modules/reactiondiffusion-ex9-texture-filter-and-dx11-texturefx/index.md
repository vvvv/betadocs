---
uid: "contribution/reactiondiffusion-(ex9.texture-filter)-and-(dx11.texturefx)"
uid-meta: "contribution/reactiondiffusion-(ex9.texture-filter)-and-(dx11.texturefx)-meta"
comments: 
 items: 
  - uid: "224057"
  - uid: "225691"
  - uid: "226004"
  - uid: "226075"
  - uid: "227888"
  - uid: "227922"
  - uid: "227933"
  - uid: "246185"
uid-files: "contribution/reactiondiffusion-(ex9.texture-filter)-and-(dx11.texturefx)-files"
title: "ReactionDiffusion - (EX9.Texture Filter) and (DX11.TextureFX)"
contribution: "true"
---

![Reaction Diffusion](https://vvvv.org/sites/default/files/imagecache/large/images/https://media.giphy.com/media/26BRH2fuCk4NHgSNW/giphy.gif) 

Hello vvvvers!

I bring you my first contribution which you will hopefully enjoy and find useful.

This is a simple implementation of the increasingly popular reaction diffusion behavior using a combination of two blurs, a blend amongst both blurs using a Substract mode, and a feedback loop through a FrameDelay node.  

You can see this behavior being used used here: 


<https://vimeo.com/145251635>

<https://vimeo.com/176261480>

Some nice features in this release are the ability to reintroduce the original texture back into the feedback loop, which enables animated textures to be used as input for some nice effects, this in combination with the ability to change between blend modes applied to the feedback loop provides a nice gamma of options to play with.

Available in both EX9 and DX11 versions.

Cheers!