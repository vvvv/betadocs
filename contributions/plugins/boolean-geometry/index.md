---
uid: "contribution/boolean-geometry"
uid-meta: "contribution/boolean-geometry-meta"
comments: 
 items: 
  - uid: "242506"
  - uid: "242513"
  - uid: "242708"
  - uid: "243269"
  - uid: "246875"
  - uid: "249880"
  - uid: "249915"
  - uid: "250464"
  - uid: "274931"
uid-files: "contribution/boolean-geometry-files"
title: "Boolean Geometry"
image: "2017-07-16-(4)_0.jpg"
contribution: "true"
---

 

   
   
        
   
   

    
  
   
   
###  Boolean operations on groups of meshes 
###  Features:
- Easily use boolean operations (union, intersect, minus, xor) on 2 or more meshes to create new objects
- Define a complex (recursive) "tree" of operations using helper nodes, see image below
- Resolve feature eliminates intersecting faces of 2 or more meshes by adding new triangles with shared edges along intersections in all input meshes, useful e.g. for [tetgen](xref:contribution/tetgen) inputs
- including helpfile{s}


  

This is a wrapper around boolean functions, i.e. CSG Tree, in libigl by the Interactive Geometry Lab @ ETH Zurich: http://libigl.github.io/libigl/


   

###  Source Code:
- the source code for the vvvv plugin plus the c++ dll can be found in my addonpack fork:
https://github.com/digitalwannabe/vvvv-sdk/tree/develop/vvvv45/addonpack/src/nodes/plugins/3d/3dConstructiveSolidGeometryTree

 
   
###  Licenses:
All my code is MIT where possible; always happy about credit to digitalWannabe/lichterloh
All code from libigl is MPL2
 
          
     

###  Changelog:
v1.0 : 
- initial release
   
   
  
