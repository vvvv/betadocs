# Transparent objects


#### Related nodes
<span class="node">Blend (EX9.RenderState Advanced)</span>  
<span class="node">ZWriteEnable (EX9.RenderState)</span>  
<span class="node">AlphaTest (EX9.Renderstate)</span>  
<span class="node">Group (EX9)</span>  
<span class="node">Group (EX9 Priority)</span>  



If you first (high priority) drew a transparent object near the camera and after that (lower priority) draw a solid object behind it, the depth buffer check would just reject the drawing of the solid object behind the transparent one - because it knows nothing about semitransparent objects.   

Make sure to draw all objects with alpha textures *after everything else* (that last sentence exactly describes the problem).   

Using a <span class="node">Group (EX9)</span> or the drawing order is determined by the order of inputs on the group node: left (first drawn) to right (last drawn). A <span class="node">Group (EX9 Priority)</span> node allows you to change the drawing order/priority programmatically via the "Priority" pins that are associated with each "Layer" input pins.  

If this turns out to be difficult, DirectX supports one classic computer graphics hack for dealing with transparent objects drawn in arbitrary order -- vvvv exposes this hack with the <span class="node">AlphaTest (EX9.Renderstate)</span> node.   

Basically it allows one to skip processing for all pixels whose alpha value is below a given reference value. This means these pixels are neither rendered nor written into the depth buffer. Connect the AlphaTest node to the render node in question, enable it, set the compare function to less (or was it greater?), and play with the "reference alpha" pin. this should cut out all transparent areas in your objects. Consult the Microsoft <a href="http://msdn.microsoft.com/library/en-us/directx9_m/directx/ref/ns/microsoft.directx.direct3d/c/renderstates/p/alphatestenable.asp" class="extURL" target="_blank">DirectX</a> documentation for details.   

Obviously this method will not give you smooth antialiased borders, but it is somehow better than nothing.   

**See also:**  
* [Transparency and Depthbuffer](TODO INTERNALLINK:transparency#where-drawing-order-matters...)  




