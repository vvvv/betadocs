---
uid: 2db04338-b1c9-4922-aada-369b238caac1
---

#  How to get a X File
## Export Plugins  for Maya
* <a href="http://www.chadvernon.com/blog/downloads/cvxporter/" class="extURL" target="_blank">for **Maya 7.x to 8.x**</a>  
* <a href="http://www.highend3d.com/boards/showflat.php?Cat=&Board=MayaGames&Number=189161&page=0&view=collapsed&sb=5&o=0&fpart=" class="extURL" target="_blank">for **Maya 6**</a>  
* <a href="http://msdn.microsoft.com/archive/default.asp?url=/archive/en-us/directx9_c_Summer_03/directx/graphics/tools/xfileexporters/mayaexporter.asp" class="extURL" target="_blank"> for **Maya 4.x and 5.x**</a>  

## Convert Maya files with third party software
* <a href="http://www.righthemisphere.com/products/dexp/de_std.html" class="extURL" target="_blank">Deep Exploration</a>   
Opens your .mb/.ma files and can save them as xFiles  

## Further resources
* <a href="http://search.msdn.microsoft.com/search/Default.aspx?brand=msdn&query=x+file+maya" class="extURL" target="_blank">MSDN Search</a> - for recent information  
* <a href="http://highend3d.com/maya/downloads/plugins/utility_external/misc/" class="extURL" target="_blank">highend3d.com</a> - List of Maya plugins  


#  Preparing files
##  Start Maya 
Load your object. Or for testing purposes, simply create a poly box (Create > Polygon Primitives > Cube). Be sure that the object is on position 0, 0, 0 if you want to map textures on it later in VVVV.  

Select your object and select File > Export Selection (with options!!). Then you'll get a window where you have to specify all export parameters.  

File Type should be XFile/cvXport, File Options should be ascii (but binary and compressed should also work).  
The Tesselation Attributes apply only for Non-Poly Objects. It's always better to convert your Nurbs or Subdiv Surfaces to Polys before starting the Export process. The output is much more predictable this way.  

Export Materials doesn't actually export the materials but the Texture Coordinates and Texture Filenames. Try it out.  

Animation is currently not supported in vvvv, so no need to export it. Skinning is also unsupported right now so uncheck this checkboxes.  

After all otions ere set, click the Export Selection Button and save your X File somewhere.  

{picture file=img/wiki_up//xfile_export1.gif}  

##  Start vvvv
Create the following nodes:   
Renderer (DX9) with a connected Camera (Transform Softimage).  
DrawFixed (EX9.Effect), X File (EX9.Geometry Load), Fill (EX9.RenderState). Connect the last two with the Draw Fixed Node.  

Right Click on the "FileName" pin of the XFile node and browse to the X File you exported earlier and a small cube will appear in your render window.  
Hold down the Z Key inside the render Window and move your mouse to zoom.  
Right click the "Fill Mode" pin on the Fill Node and select "Wireframe"  
Hold down the R Key inside the render Window and move your mouse to rotate arround the cube.  

Now try some other geometry  

#  Subsets
Subsets are different and seperated parts of a single object. For example you can have a teapot, where the can is seperated from the cap. Or a cube, which consists of 6 quads.  
The benefit is, that vvvv can manipulate every single subset (for example translate only the cap of the teapot and leaving the can in place) or the whole object.  

To define, which part of an object belongs to a subset, you have to assign tifferent materials to the different parts (vertices, edges, faces, objects) of your scene.  

#  Start Maya
First create another cube.  
Open your Hypershade (Window > Rendering > Hypershade)  
Create a new material, or better 6 materials.  
Select a face of the cube and assign material 1 to that face. Then select the next face of the cube and assign material 2. Go on untill every face of the cube has a different material.  

{picture file=img/wiki_up//xfile_export2.jpg}  

Select the cube as object and then export it (File > Export Selection, with options)  

##  Start vvvv
Load the X File in the previously created patch and you won't notice any change. The imported object is still a ordinary cube.  

But when you connect a Count (EX9.Geometry Mesh) to the XFile Node, you will notice a subset count of 7. Why seven and not 6? Because the default material (Lambert1) counts also as subset, even if there is no geometry to which it applies.  

Connect a Linear Spread to a Translate Node and connect the Translate Node with the Draw Fixed node.  
Play arround with the slicecount of the LinearSpread and you will see, that every face of the cube gets translated individually.  

See the example patch, including a box.x, on the <a href="http://vvvv.org/tiki-index.php?page=User+Tutorials" class="extURL" target="_blank">User Turorials Page</a>