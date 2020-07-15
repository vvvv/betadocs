---
uid: 985d35ea-6b69-4aaf-a5e3-9f9978ac03a2
---

# Meshes



#### Related nodes
<span class="node">Xfile (EX9.Geometry load)</span>  
<span class="node">ColladaFile (EX9.Geometry)</span>  
<span class="node">Scene (Assimp)</span>  



### Loading Meshes

vvvv can natively load meshes exported from 3D Modelling Software (like Blender, Maya, Cinema4D) in the **XFile** (*.x) or **Collada** (*.dae) formats. Skeletons, Animations, Cameras are also available in the Collada format.  

Via the *Assimp* category of nodes a <a href="http://assimp.sourceforge.net/main_features_formats.html" class="extURL" target="_blank">large list of 3d-formats</a> can be imported alternatively.   

**The Assimp-nodes are contributed by <span class="user"><a href="https://vvvv.org/users/vux" class="extURL" target="_blank">vux</a></span> and are coming with the <a href="https://vvvv.org/downloads#addonpack" class="extURL" target="_blank">addonpack</a>.**  

Examples in your vvvv\girlpower\ directory:  
* Graphics\DX9\Geometry  

**See also:**  
* [How to work with Collada](xref:c9f8e059-dcf9-4712-a877-a200b17d7f76)  
* [How to work with XFiles](xref:3ac2ed1f-db6d-4f0f-8679-80183ab51517)  
* <a href="https://vvvv.org/contributions/1353+1351+2439+1352+7934+2438+1354+1355/8106+5207+2063+1679+3453" class="extURL" target="_blank">Related Contributions</a>  





#### Related nodes
<span class="node">Mesh (EX9.Geometry Join)</span>  
<span class="node">Mesh (EX9.Geometry Split)</span>  
<span class="node">VertexBuffer (EX9.Geometry Join)</span>  
<span class="node">VertexBuffer (EX9.Geometry Split)</span>  
<span class="node">Normals (EX9.Geometry Mesh)</span>  
<span class="node">MeshEditor (EX9)</span>  
<span class="node">GridEditor (EX9)</span>  
<span class="node">PickPoints (3d Vector)</span>  


### Dynamic Meshes

You can use the basic built-in geometries from the 'EX9.Geometry' category as a starting point and then manipulate / add / remove vertices and indices or create everything from scratch.  

A **Mesh** is a data container with two distinct parts: IndexBuffer and VertexBuffer  

* the IndexBuffer is a list of integer number triplets where each triplet defines a triangle of the Mesh and each integer number referes to a vertex in the VertexBuffer.  
* the VertexBuffer is a list of all vertices in the Mesh.  

A **Vertex** is a container itself for data like position, orientation (normal), texture coordinates and so on. But vertex is also often used as a synonym for a 3d position, as the position data is the most important part of it, because with it the shape of the Mesh is defined.  

Examples in your vvvv\girlpower\ directory:  
* Graphics\DX9\Geometry  

**See also:**  
* <a href="https://vvvv.org/contributions/1353+1351+2439+1352+7934+2438+1354+1355/8106+5207+2063+1679+3453" class="extURL" target="_blank">Related Contributions</a>  



