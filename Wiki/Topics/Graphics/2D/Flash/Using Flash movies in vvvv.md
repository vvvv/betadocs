# Using Flash movies in vvvv


#### Related nodes
<span class="node">HTMLTexture (EX9.Texture String)</span>  
<span class="node">HTMLTexture (EX9.Texture URL)</span>  
<span class="node">Flash (EX9.Layer)</span>  
<span class="node">Renderer (Flash)</span>  



There are 3 ways to use <a href="http://www.adobe.com/de/products/flash.html" class="extURL" target="_blank">Flash</a> in vvvv, each of the options has its pros and cons:  

---  

#### HTMLTexture (EX9.Texture)
This node is wrapping <a href="http://en.wikipedia.org/wiki/Google_Chrome" class="extURL" target="_blank">google's chrome webbrowser</a> and as such returns everything chrome can display as a ready-to-use texture.  

**HTMLTexture node is coming with the <a href="https://vvvv.org/downloads#addonpack" class="extURL" target="_blank">addonpack</a>.**  

**Known problems:**  
1. Mouse interaction is not always working properly.
1. Use of semi-transparent Flash movies as textures with alpha-channel is broken (in the underlying library).

If you encounter these problems, stick to the old <a href="https://vvvv.org/blog/vvvv45beta32.1" class="extURL blog" target="_blank">beta32.1 version</a> for now and check the 'IO\Web\07_Transparent Flash' example from its 'girlpower' directory.  

---  

#### Flash (EX9.Layer)
Returns the flash content as a vvvv layer. Takes mouse and keyboard as inputs.   

Requires the (old) Flash Activex Control 10.0 to be installed. If you have a newer one see   
<a href="https://discourse.vvvv.org/t/drawflash-plugin-not-working" class="extURL forum" target="_blank">drawflash-plugin-not-working</a>  
for how to downgrade to 10.  

---  

#### Renderer (Flash)
Renders the flash content in its own window. <span class="node">GDITexture (EX9.Texture)</span> can be connected to get the content as a texture. This option allows you to directly set/get variables to/from the flash movie.  

The Renderer uses the Flash ActiveX control to embed the flash player into the flash renderer node. This means VVVV can use the latest flash versions and all its features. In order to get the latest ActiveX control you need to open Internet Explorer and upgrade flash from there.  

For an alternative ways of passing variables to flash see:   
* <a href="http://benchun.net/projects/flosc/" class="extURL" target="_blank">flosc</a>   
* <a href="http://blog.derhess.de/2011/08/16/flash-talks-to-max-msp-via-osc/" class="extURL" target="_blank">Flash talks to MAX/MSP via OSC</a> (the same technique can be used for vvvv).  
* [Using OSC in vvvv](TODO INTERNALLINK:protocols#osc)  

