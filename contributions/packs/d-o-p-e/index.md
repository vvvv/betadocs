---
uid: "contribution/d.o.p.e."
uid-meta: "contribution/d.o.p.e.-meta"
comments: 
 items: 
  - uid: "230933"
  - uid: "230940"
  - uid: "230945"
  - uid: "230974"
  - uid: "231868"
  - uid: "232714"
  - uid: "232928"
  - uid: "232933"
  - uid: "233451"
  - uid: "234049"
  - uid: "234871"
  - uid: "241293"
  - uid: "241298"
  - uid: "246876"
  - uid: "246892"
  - uid: "271597"
  - uid: "271646"
  - uid: "271755"
uid-files: "contribution/d.o.p.e.-files"
title: "d.o.p.e. [dope]"
image: "_30.10.2016-04.07.17.gif"
contribution: "true"
---

 

   
   
        
   
   

    
  
   
   
###  Shape-aware blend weight computation for 2D/3D meshes

###  Features:

- Input can be either triangulated 2D meshes or 3D volumetric meshes
- Supported control handles: single points, connected bones and cages (of arbitrary topology)
- Control handles can be translated, scaled and rotated
- Output can be used in blend skinning shaders for realtime performance
- Includes forward kinematics solver for rotating bones
- supports Instancing (incl. Noodles)
- girlpower, check it out!

  
This pack comes with several nodes:

-BoundedBiharmonicWeights: this is where the magic happens
-ForwardKinematics: a simple forward kinematics solver for rotating bones
-MatrixMultiplication: mainly used for debugging blend weights (and for now the only DX9 solution)
-LinearBlendSkinning: a shader for rendering, atm DX11 only

Also included in this pack are previous plugins of mine: [triangle](xref:contribution/triangle), [tetgen](xref:contribution/tetgen) and [mix-(transform)](xref:contribution/mix-(transform)) as they are useful helpers here and essential for some examples.

d.o.p.e. is based on research and code from the Interactive Geometry Lab @ ETH Zurich, ie "Bounded Biharmonic Weights for Real-Time Deformations": http://igl.ethz.ch/projects/bbw/


   

###  Source Code:

[https://github.com/digitalwannabe/d.o.p.e.](https://github.com/digitalwannabe/d.o.p.e.)

 
   
###  Licenses:

All my code is MIT where possible; always happy about credit to digitalWannabe/lichterloh
All code from libigl is MPL2


  

###  ToDo:

- Pseudo edges; from the original research: linear transform helpers for point handles, which infer point rotations from their translations
- DX9 version of linear blend skinning shader
- Solution for normals
- Dual quaternion skinning shaders for smoother rotation results
- custom datatype to avoid huge spreadcounts
- improve RemovRegions (Triangle + TetGen) performance, no good
- run BoundedBiharmonicWeights on a different process to avoid blocking of vvvv
- png2poly

 
          
     

###  Changelog:

v1.2 :
- added support for instancing (incl. hack for noodles), see 3D girlpower folder
- updated triangle/tetgen
- now works in beta (50+)


v1.1 :
- fixed x64 precision error in girlpower patch


v1.0 : 
- initial release
   
   
   

###  known bugs:

- the linear blend skinning shader shows an error on startup, not sure why yet....only applies to alpha versions....

    
<div class="box">
Note:
NOTE: All girlpower examples require DX11 (for now!), see the help patch of the BoundedBiharmonicWeights node for a DX9 (CPU-only) version. DX9 shaders coming soon!
</div> 



    
    
    
Nothing works? Try installing this: https://www.microsoft.com/en-us/download/details.aspx?id=48145
