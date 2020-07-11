---
uid: 93b2f838-bbd4-423c-81cb-09820d98537d
---

# Video Effects (TextureFX)


#### Related nodes:
<span class="node">Glow (EX9.Texture Filter)</span>  
<span class="node">Blur (EX9.Texture Filter)</span>  
<span class="node">Stripes (EX9.Texture Filter)</span>  
<span class="node">Tunnels (EX9.Texture Filter)</span>  
<span class="node">ShiftRGB (EX9.Texture Filter)</span>  
<span class="node">Polygonize (EX9.Texture Filter)</span>  

<span class="node">Perlin (EX9.Texture Source)</span>  
<span class="node">Pillow (EX9.Texture Source)</span>  
<span class="node">Lava (EX9.Texture Source)</span>  
<span class="node">Elektricity (EX9.Texture Source)</span>  

<span class="node">Mix (EX9.Texture Mixer)</span>  
<span class="node">Blend (EX9.Texture Mixer)</span>  
<span class="node">Blood (EX9.Texture Mixer)</span>  

...and many **many** more.  



TextureFX is essentially vvvvs answer to <a href="http://freeframe.svn.sourceforge.net/viewvc/freeframe/trunk/docs/specification.html" class="extURL" target="_blank">freeframeGL</a>, i.e. a specification for modules that do GPU-based texture-generation, -manipulation and -analysis.  

It's like using filters and layers in Photoshop or AfterEffects, but interactively and in real-time (ie. GPU-based).  

Every video is just a sequence of textures, so there is no difference whether the effects are applied to the static images or to the video streams (represented as textures).  

The whole series of modules/effects is now part of the [Addonpack](TODO INTERNALLINK:downloads). Type 'fx' in the [NodeBrowser](TODO INTERNALLINK:the-gui#node-browser) to get the full list of available nodes.  

The idea was triggered by <span class="user"><a href="https://vvvv.org/users/karistouf" class="extURL" target="_blank">karistouf</a></span> in his thread with the almost poetic title <a href="https://discourse.vvvv.org/t/pure-image-treatment-question-wich-evolution-for-vvvv)) and implementation is expertly lead by <span class="user"><a href="https://vvvv.org/users/unc" class="extURL forum" target="_blank">pure-image-treatment-question-wich-evolution-for-vvvv" class="extURL" target="_blank">unc" class="extURL forum" target="_blank">pure-image-treatment-question-wich-evolution-for-vvvv</a></span> and implementation is expertly lead by ((user:unc</a>.  

Examples in your vvvv\girlpower\ directory:  
* Graphics\DX9\Textures  

**See also:**  
* [TextureFX Specification](TODO INTERNALLINK:texturefx)  
* <a href="https://vvvv.org/contribution/video-effects-and-compositing-tutorials" class="extURL contribution" target="_blank">Video Effects and Compositing Tutorials</a>  
* <a href="https://vvvv.org/contributions/1353+1351+2439+1352+7934+2438+1354+1355/5693+1584+2750+1583+2399+4175" class="extURL" target="_blank">Related Contributions</a>  


