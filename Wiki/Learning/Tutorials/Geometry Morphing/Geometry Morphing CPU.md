---
uid: 772f4282-a62a-467a-938a-d3f69bf3f57b
---

# the cpu based approach

as you may have already heard already. when morphing geometry it is necessary to have two 3d models that do not only consist of the same number of vertices. those vertices should also be indexed (ordered) the same way. if one of those prerequisites is not met you can still morph the models and may even get more interesting results.   

creating equally indexed 3d models with your favorite modelling software is a task of its own. for this tutorial we will just morph between two primitive cones that ship with vvvv. and patch we do:  

## preparing the morphtargets

first build a patch that simply renders two cylinders on top of each other. a red one and a green one. one straight. the other upside down. our two morphtargets. patch until you have something like pictured below.  

![](~/img/cpu_012_3.jpg "")  

note the <span class="node">Camera (Transform Softimage)</span> and <span class="node">AspectRatio (Transform)</span> nodes that are not essential here but are just a good idea to have anyway.  

when hovering the cylinders output you see that its connection to the <span class="node">GouraudDirectional (EX9.Effect)</span> is a mesh connection. a mesh consists of a vertex- and an index buffer. whereas the indexbuffer in vvvv is represented as a simple spread the vertexbuffer is kind of a container for several components making up the geometry. connecting a VertexDeclaration (EX9.Geometry Mesh) node to the cylinder and hovering its output shows you what vertexcomponents our cylinder consists of: there are Position, Normal and TextureCoordinate values in the cylinder mesh. other meshes can include <a href="http://msdn.microsoft.com/library/default.asp?url=/library/en-us/directx9_c/D3DDECLUSAGE.asp" class="extURL" target="_blank">other components</a>.   

now there isn't yet a node in vvvv that would just take 2 meshes and a morph-factor and do the work for us. and since there will probably never be such a node (because it is a boring thing to implement) and since you want to know how everything works anyway we now just patch exactly what such a node would do.   

## accessing the vertexbuffer

therefore we need a node to access all the components of a mesh so that we can patch the morphing manually. see the patch below how we can use a <span class="node">Mesh (EX9.Geometry Split)</span> followed by a <span class="node">VertexBuffer (EX9.Geometry Split)</span> to read out all the vertex data. the patch also demonstrates that this process can be reversed. <span class="node">Mesh (EX9.Geometry Join)</span> followed by a <span class="node">VertexBuffer (EX9.Geometry Join)</span> assamble the cylinder back to a valid mesh for the <span class="node">GouraudDirectional (EX9.Effect)</span> to render.  

![](~/img/cpu_021_3.jpg "")  

note the indexbuffer coming out of <span class="node">Mesh (EX9.Geometry Split)</span> being directly connected to <span class="node">Mesh (EX9.Geometry Join)</span> and the vertexbuffers position and normals components handed over from the splitting to the joining VertexBuffer node.   

## doing the morph

seeing this you may have already figured out how we have to go on now. we are only missing the morphing part between the two VertexBuffer nodes. split the green cylinders vertex-data as you did with the red one and use a simple <span class="node">InputMorph (Value)</span> for the morphing.  

![](~/img/cpu_031_3.jpg "")  

since the color is not a component of the vertexbuffer but a parameter for the effect you have to do the morphing for the color separately with an <span class="node">InputMorph (Color)</span> node. dragging the inputmorph's value between 0 and 1 now results in a smooth blend from a regular red cylinder to an upsidedown green cylinder. questions?  

>note:  
with this approach all the calculation of the morphed positions and normals is done on the CPU. also a new vertexbuffer and/or mesh is created every frame the "Apply" pin is 1 on the respective nodes which costs some time.   

this poses no problem as long as you are working with relatively small meshes. if you get the feeling that everything is getting a bit slow read on about the cooler [gpu based](TODO INTERNALLINK:Tutorial Geometry Morphing GPU1) approach.  
  

## bonus

see what happens if you have two models that do not correspond in vertexcount and indices. double click the first Cylinder node and replace it with a <span class="node">Teapot (EX9.Geometry)</span> node. instant media art!  

![](~/img/cpu_040_3.jpg "")  
