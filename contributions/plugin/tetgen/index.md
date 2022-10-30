---
uid: "contribution/tetgen"
uid-meta: "contribution/tetgen-meta"
comments: 
 items: 
  - uid: "223939"
  - uid: "223951"
  - uid: "223955"
  - uid: "223960"
  - uid: "223972"
  - uid: "225089"
  - uid: "225092"
  - uid: "225116"
  - uid: "225121"
  - uid: "225123"
  - uid: "225132"
  - uid: "225376"
  - uid: "225637"
  - uid: "226015"
  - uid: "226492"
  - uid: "226534"
  - uid: "226540"
  - uid: "226560"
uid-files: "contribution/tetgen-files"
title: "TetGen"
image: "tetgen2_invert.jpg"
contribution: "true"
---

  
### A Quality Tetrahedral Mesh Generator and a 3D Delaunay Triangulator
TetGen generates tetrahedral (volumetric) meshes and 3d delaunay triangulations from PLC's (piecewise linear complexes), which essentially are sets of 2d polygons describing the boundaries/hull/surface of a 3d geometry. These polygons are given by their corner points plus indices (in clockwise or counter-clockwise order).

The resulting data (points plus triangular indices) can be used to create a mesh in vvvv. For volume-dependent calculations (my actual use case;)) tetrahedral indices will be output too.

Holes and regions (with differing meshing quality/density) are supported. The 'r' switch (refining existing tetrahedral meshes) is not supported by this plugin.
Optionally input and output files can be written to disk (*.poly,*.node,*.ele,*.face, see [ here](http://wias-berlin.de/software/tetgen/1.5/doc/manual/manual006.html#sec69%20)), see Inspector for options.

Fully spreadable, with helpfile(s).


All information on TetGen can be found here:
www.tetgen.org


All switches, which are needed to control the behaviour of TetGen, ie the meshing quality/density, can be found here:
http://wias-berlin.de/software/tetgen/switches.html





   

###  ToDo:
(reminder to myself)

- file reader for *.poly,*.node,*.ele,*.face files
- support the 'r' switch
- improve RemovRegions performance, no good
- support point metrics, point attributes (tried nut no luck), facet constraints, segment constraints, etc.
- run TetGen on a different process to avoid blocking of vvvv (meshing simple geometries might even work in realtime...)
- normals in dx11 (?)
- check if spreading actually works ;)



    

###  Source Code:
As I always struggle (again) to find out eg how Interop between C++ and C# works (and a lot of other plugin related stuff) I'm sharing the full source code here. Be aware, no guarantee any of this is done the way it actually should be done (especially don't copy any of my nuget, addonpack or compiler related settings: i have no idea :)....all input welcome of course!
- the source code for the unmanaged "TetGen2vvv.dll", which itself calls "tet.lib"(included, compiled with TetGen v1.5 from www.tetgen.org), can be found here:
https://github.com/digitalwannabe/TetGen4vvvv
- the source code for the vvvv plugin, which calls the unmanaged "TetGen2vvvv.dll" can be found in my addonpack fork:
https://github.com/digitalwannabe/vvvv-sdk/tree/develop/vvvv45/addonpack/src/nodes/plugins/3d/3dTetrahedralize



   

###  Licenses:
All my code is MIT where possible
TetGen is licensed under AGPLv3, find info on licensing TetGen [here](http://wias-berlin.de/software/tetgen/1.5/FAQ-license.html)

   
   
   
###  Changelog:
v1.03 :
-new input: vertex marker
-new outputs: vertex markers, face markers, region attributes, tetrahedron neighbors
-new helper node: RemoveRegion, with helpfile. needs performance improvement though

v1.02 :
compiled with /MT to support older vs

v1.01 : 
-bug fixes

v1.0 :
-initial release
 
  


###  Installation Note:
Always copy the dependencies folder (+helpfiles) with the plugin!
  
