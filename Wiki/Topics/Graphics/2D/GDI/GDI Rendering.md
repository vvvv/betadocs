# GDI Rendering
GDI Rendering is designed to be quick and simple. Some simple nodes will create text and rectangles, as well as lines and Bézier curves. The coordinate system is a square going from (-1, -1) in the lower left corner to (1, 1) in the upper right corner.  

To play with the GDI renderer, create a <span class="node">Renderer (GDI)</span> node and use the following nodes. Most should be fairly self explanatory, especially if you open their help patches.    

![](~/img/rendering_01_3.png "")  

The <span class="node">HLine (GDI)</span>, <span class="node">VLine (GDI)</span> and <span class="node">Point (GDI)</span> nodes are meant for simple demonstration patches to mark horizontal and vertical lines and points.   

There is a group of nodes in the Debug category, which are used for quick performance and status messages. While they are ready for a general overhaul, they will usually print out status information to the GDI renderer.