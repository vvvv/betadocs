---
uid: c9f8e059-dcf9-4712-a877-a200b17d7f76
---

# Collada
## Table of contents

---  

## Overview
The collada plugin enables vvvv to import <a href="http://collada.org" class="extURL" target="_blank">COLLADA</a> documents (version 1.4). It was developed to meet version 1.4.1 of the <a href="http://www.khronos.org/files/collada_spec_1_4.pdf" class="extURL" target="_blank">collada specification</a>.  

Currently supported features are:  

* Mesh geometry - Mesh must be made out of triangles or polylists.  
* Skinning - Supports up to 60 bones.  
* Animation - Linear and bezier.  
* Materials  

Still missing features:  

* Morphing  
* COLLADA FX (effects and shaders)  
* COLLADA Physics  

---  

## User Guide
### Installation
The collada plugin is shipped with the vvvv addon pack. For instructions how to install the addon pack see [Downloads](https://vvvv.org/downloads).  

### Quickstart
Use node ColladaFile (EX9.Geometry) to load a *.dae file and use node Mesh (EX9.Geometry Collada) to work on that loaded Collada model. See help patch of node Mesh (EX9.Geometry Collada) for an example.  

### Node reference
If you've installed this plugin successfully the following nodes should be in your node list.  

#### ColladaFile (EX9.Geometry)
Loads a COLLADA file (*.dae) into memory. Its ouput (so called COLLADA Model) represents the loaded file and is the basis for all the other collada nodes.  
##### Input pins
* Filename COLLADA file (*.dae) to load.  
##### Config pins
* Coordinate system of source - Use this pin if you want to override the orientation of the coordinate system of the 3D scene stored in the COLLADA file.Value 'Default' specifies a right handed coordinate system (specified by COLLADA standard).   
* Source up axis - Use this pin to set the up axis of the coordinate system.Value 'Default' reads up axis from COLLADA file. If there is no up axis defined Y is taken.   
* Source right axis - Use this pin to set the right axis of the coordinate system.Value 'Default' reads right axis from COLLADA file. If there is no right axis defined X is taken.   
* Source distance unit in meter - How many real word meter is one distance unit. For example 1 km are 1000 m or 1 cm are 0.01 m.Value '0' means that it is read from COLLADA file.   
* Coordinate system of target - Use this pin if to set the orientation of your coordinate system.Value 'Default' is left handed (DirectX standard).   
* Target up axis - Use this pin to set the up axis of your coordinate system.Value 'Default' is Y (DirectX standard).   
* Target right axis - Use this pin to set the right axis of your coordinate system.Value 'Default' is X (DirectX standard).   
* Target distance unit in meter - How many real word meter is one distance unit in your patch. For example 1 km are 1000 m or 1 cm are 0.01 m.Value '0' means that default is used which is 1.0.   
##### Output pins
* COLLADA Model - Provides data of COLLADA file for subsequent nodes like Mesh (EX9.Geometry Collada) etc.   
* Info - A string pin which holds information about the loaded COLLADA file. Should be pretty self-explanatory.The in axis is the axis into your monitor.Maybe extended in the future.   

#### Mesh (EX9.Geometry Collada)
This node extracts mesh geometries stored in the COLLADA file in form of one X Mesh. To distinguish between the different mesh geometries a subset is generated for each of them. Since it's possible in COLLADA that a mesh can be made out of different mesh parts (for example to assign different materials for each part of a mesh), there are also subsets generated for each of those mesh parts.  
Please see [Meshes](xref:c9f8e059-dcf9-4712-a877-a200b17d7f76#meshes-in-collada-and-vvvv) in COLLADA and vvvv] for more detailed explanation how to work with COLLADA geometries in vvvv.  
##### Input pins
* COLLADA Model - COLLADA Model where the mesh is extracted from. Provided by node ColladaFile (Ex9.Geometry).   
* Time - If the geometries in COLLADA are animated this pin can be used to set the animation time. Influences the transformation and skinning matrices. Note that this pin can be spreaded.   
* BinSize - Defines how many meshes are selected by one index. Default is -1, which means that all meshes stored in the COLLADA file are selected. Not spreadable.   
* Index - Defines the mesh selection. Default is 0. Use in combination with BinSize pin.   
##### Config pins
* Opaque=1? - Use this pin to define if 0 or 1 is seen as opaque in a material. This depends on the used collada exporter.   
* Skeleton pin enabled - If the skeleton pin should be enabled. Default false for performance reasons.   
##### Output pins
* Mesh - The X Mesh for further use in vvvv.   
* Tranforms - Tranformation matrix for each subset of the X Mesh.   
* Skinning - Transforms If the COLLADA file contains skinned meshes and these meshes are selected by this node than this pin will hold all the skinning matrices needed by a subsequent effect node with skinning support (Skinning.fx for example).   
* TextureFileName - Filename for texture to be used by each subset of X Mesh.   
* Emissive Color  
* Diffuse Color  
* Speculat Color  
* Power - All these four pins describe the material for each subset.   
* Opaque - This pin is 0 for complete transparent materials and 1 for opaque ones.   
* Skeleton - If the config pin 'Skeleton pin enabled' is true then this pin will output a spread of points to be able to visualize the skeleton (for example with node Line (EX9.Geometry) with bin size set to 2).   

#### Skeleton (Skeleton Collada)
If available in the COLLADA file, this node returns the skeleton selected via the <span class="pin">Index</span> pin. Have a look at the skeleton nodes to get further details on this: [Skeleton Animation Nodes](xref:4c4a36ab-7a01-45dc-a4f9-9ed88c319918)  

#### Camera (EX9.Geometry Collada)
If available in the COLLADA file, this node returns a view and projection matrix for the camera selected via the <span class="pin">Index</span> pin. Those matrices can directly be connected to the <span class="node">Renderer (EX9)</span>.  

### Meshes in COLLADA and vvvv
In COLLADA multiple meshes can be defined and each mesh can consist of multiple subsets while in vvvv there can only be one mesh with multiple subsets. To still be able to display all meshes defined in a COLLADA document in vvvv, all meshes are concatenated and a subset is generated for each of them.  
Formally the situation can be described as follows:  
 subsets_in_vvvv(n) := SUM(i := 1 .. n)(subsets(i))
where n is the number of meshes in COLLADA  
and subsets(i) is the number of subsets of mesh i   
Please keep this in mind if you work with more complex COLLADA files and use the Index pin of Mesh (EX9.Geometry Collada) to select individual COLLADA meshes and GetSlice (Node) to address individual subsets of a selected mesh.  

### Skinning
Skinning is a technique in 3D authoring tools which binds a static mesh (the skin) to a skeleton, which can easily be animated. Technically speaking each vertex of the skin is associated with one or more bones of the skeleton and each bone influences the position of the vertex dependent on a weight factor.  
This means that each vertex of the skin has to be multiplied by a few transformation matrices of its influencing bones in every frame. Because usually a mesh consists of a few thousand vertices this task could be a very slow one, would it be done on the CPU (software skinning).  
That's why it's done in hardware and that's why it's not as easy to setup in vvvv as a scene made up of static meshes, but it's not very hard either.   
All you have to do is using a vertex shader, which does the above mentioned multiplications, and feed it with the skinning matrices you get from Skinning Transforms ouput pin of Mesh (EX9.Geometry Collada). For a starting point see the **Skinning.fx** effect node.  

Note that each vertex can address up to four bones and the skeleton must not have more than 60 bones.  

### Notes on export in external applications
#### 3D Studio MAX
3D Studio MAX (at least 2010) supports export of COLLADA files but what I've seen it's not perfect. For example if you use the Physique modifier to skin a character, the export will not work. Instead you'd have to use the Skin modifier.
Additionally it uses polygons as primitives for exported meshes, which is not supported by this plugin (the COLLADA specification states that that polygon should only be used in special cases). See topic Error Messages for an explanation how to load COLLADA files which store its meshes as polygons.  

A better way is to use the <a href="http://www.opencollada.org" class="extURL" target="_blank">OpenCOLLADA</a> plugin. Its export mechanism supports triangles, the Physique modifier can be used and it's much faster as the native exporter too. Exported COLLADA file should work flawlessly in vvvv.  

Download OpenCOLLADA<a href="https://github.com/KhronosGroup/OpenCOLLADA/wiki/OpenCOLLADA-Tools" class="extURL" target="_blank">here</a>.  
Alternatively try: <a href="http://www.kwxport.org/" class="extURL" target="_blank">Kwxport</a>.  

#### Maya
Download OpenCOLLADA<a href="https://github.com/KhronosGroup/OpenCOLLADA/wiki/OpenCOLLADA-Tools" class="extURL" target="_blank">here</a>.  

#### Blender
Scenes with static meshes exported fine. No luck with character rigs, which use skinned meshes. Didn't try animations. Here is an alternative exporter: <a href="http://www.godotengine.org/wp/better-collada-exporter/" class="extURL" target="_blank">Better Collada Exporter</a>  

### Error messages
If a collada file won't load open the terminal (Renderer (TTY)) and have a look at the error messages and see if it is listet in the following list.  

* **polygons type not supported** Currently there is only support for the triangle and polylist primitives. See if your exporter has an option to export your mesh as triangles or a polylist. If your exporter doesn't have such an option have a look at the tool <a href="http://www.collada.org/mediawiki/index.php/Refinery" class="extURL" target="_blank">COLLADA Refinery</a>. It is a very powerful tool, which can amongst others convert polygons to triangles. On the left side select Macros->toTriangles, connect the pins and execute.Unfortunately it is a little buggy, so in some situations it will convert for example only the half of your mesh ;(   

If your error message is not listed above or there isn't even an error message please feel free to open up a new topic in our forums.  

---  

## Development Guide
The source code of the plugin is split into two projects, ColladaSlimDX and ColladaLoader.   

The source code can be retrieved with subversion at:  
* ColladaSlimDX https://github.com/vvvv/ColladaSlimDX   
* ColladaLoader https://github.com/vvvv/vvvv-sdk/tree/develop/vvvv45/src/nodes/plugins/Mesh/ColladaLoader   

The directory structure should look like this:  
 misc/ColladaSlimDX
plugins/_PluginInterfaces  
plugins/_Utils  
plugins/_SharedSources  
plugins/Mesh/ColladaLoader   

### Project ColladaSlimDX
ColladaSlimDX is based on the work of <a href="https://collada.org/public_forum/viewtopic.php?t=676" class="extURL" target="_blank">COLLADA for XNA</a> but was rewritten for <a href="http://slimdx.mdxinfo.com/" class="extURL" target="_blank">SlimDX</a> and modified and extended in a few ways. Its purpose is to parse a COLLADA file, build a DOM tree (ColladaDocument) and provide some "nice" methods to work with all the different collada objects (ColladaModel). In short: the dirty work.  
To see how to use it please have a look at source code of ColladaLoader.   
#### COLLADADocument class
This class holds the DOM tree of the COLLADA file. For nearly every tag defined in the COLLADA specification exists a related class of the same name with all the members and children defined.  
#### COLLADAUtil class
This class provides a few helper methods to make access to the DOM tree easier. At first glance those methods might seem a little confusing, but if you dig deeper into COLLADA and expirience all those little details which make a programmers life miserable they might become quite handy in some situations. See the source code for a few examples.  
Of course new methods are always welcome!  
#### COLLADAModel class
The COLLADAModel class is probably the hardest part. In a COLLADA document things are organised in libraries. For example the library_geometries holds all the geometry objects, which can be meshes or splines. Or the library_materials holds all the materials which can be assigned to a geometry. So this is the first task, to read out all these objects in these libraries and store them in dictionaries (key, value pairs) for later lookup.  
Now that all objects are known or let's better say, all objects we want to know about (for example lights or cameras are ignored at this point) are known we can process the most important scene object. Eventually this one tells us which geometries take part in the scene, what materials should be assigned to them etc.  

The scene object provides a scene graph, which is a tree actually and each node of that tree holds (but must not) transform information (translation, rotation, scaling, etc.) and the leaves of the tree tell us what geometry, light, camera, controller (for skinning or morphing) or as well other subtree should be placed here.  
It is also at this point where the material binding takes place.  

For further explanation please have a look at the <a href="http://www.khronos.org/files/collada_spec_1_4.pdf" class="extURL" target="_blank">collada specification</a> or the <a href="https://collada.org" class="extURL" target="_blank">collada homepage</a>.  


### Project ColladaLoader
ColladaLoader is the actual vvvv plugin. Currently it provides two nodes, ColladaFile (EX9.Geometry) and Mesh (EX9.Geometry Collada).  

#### ColladaFile node
The ColladaFile node is very simple. It gets a filename string as input, creates a ColladaDocument and uses that to create a ColladaModel object which is consumed via a node pin by the collada mesh nodes.  

#### Mesh node
The Mesh node is a little more complex. Basically it takes a ColladaModel object and uses the objects helper methods to create a Direct3D9 mesh which then can further be used by vvvv.  
There is a little problem though: in a COLLADA file multiple meshes can be defined, but vvvv can only handle one mesh. To overcome this little inconvenience all the meshes defined in COLLADA have to be joined to one mesh. Fortunately DirectX is so kind to provide such a method.  
To still be able to distinguish all the different collada mesh objects in vvvv, each one is assigned to a different subset.  
In vvvv a subset of a mesh is treated in the exact way like a slice of a spread (all that modulo stuff).  
That way it's possible to assign materials (color and texture information) and transforms to each mesh (subset).  

---  

## Tools
* <a href="http://colladaloader.sourceforge.net/" class="extURL" target="_blank">colladaloader</a> simple collada viewer. seems quite robust at first glance, displaying most of the files found so far.  
* <a href="http://www.collada.org/mediawiki/index.php/COLLADA_Asset_Manager" class="extURL" target="_blank">COLLADA Asset Manager</a> doesn't show any file correctly but has a document-treeview  
* <a href="http://developer.nvidia.com/object/FX_Composer_Home.html" class="extURL" target="_blank">NVIDIA FXComposer</a> has document-treeview  
* <a href="http://symbolclick.com" class="extURL" target="_blank">XMLMarker</a> a nice XML editor to view a COLLADA file for debugging reasons.  
* <a href="http://code.google.com/p/collada-web-viewer/" class="extURL" target="_blank">COLLADA Web Viewer</a> based on googles O3D plugin   

## File Examples
* The <a href="https://collada.org/owl/browse.php?sess=0&parent=28&expand=1&order=name&curview=0&sortname=ASC" class="extURL" target="_blank">COLLADA Test Model Bank</a> is a site where people working on COLLADA-related projects can get and exchange test models.