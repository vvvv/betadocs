---
uid: "contribution/triangle"
uid-meta: "contribution/triangle-meta"
comments: 
 items: 
  - uid: "223452"
  - uid: "223454"
  - uid: "223455"
  - uid: "223456"
  - uid: "223458"
  - uid: "223477"
  - uid: "223666"
  - uid: "223672"
  - uid: "223682"
  - uid: "223693"
  - uid: "223699"
  - uid: "223744"
  - uid: "223799"
  - uid: "223809"
  - uid: "223833"
  - uid: "223934"
  - uid: "223937"
  - uid: "223952"
  - uid: "230301"
  - uid: "230901"
  - uid: "233937"
  - uid: "234874"
  - uid: "270562"
  - uid: "270563"
  - uid: "270739"
uid-files: "contribution/triangle-files"
title: "Triangle"
image: "triangle_vvvv2.jpg"
contribution: "true"
---

###  A 2d Quality Mesh Generator and Delaunay Triangulator
Triangle creates 2d delaunay triangulations of "Planar Straight Line Graphs", which basically are 2d polygons. These polygons are given by their corner points (in clockwise or counter-clockwise order).

The resulting data (2d points in structured order) can be used to create a mesh in vvvv.

Holes are supported. 
Fully spreadable, with helpfile(s).

All information on Triangle and Triangle.net can be found here:
https://www.cs.cmu.edu/~quake/triangle.html
https://triangle.codeplex.com/

   

###  Source Code:
https://github.com/digitalwannabe/vvvv-sdk/tree/develop/vvvv45/addonpack/src/nodes/plugins/2d/2dTriangle

   
###  Licenses:
All my code is MIT
Triangle.net is MIT

  

###  ToDo:
(reminder to myself)

-file reader for *.poly files
-support refining existing meshes
-improve RemovRegions performance, no good
-run Triangle on a different process to avoid blocking of vvvv
-extrude mesh feature would be nice and not too hard to do...
-png2poly

 
          
     

###  Changelog:
v1.3 :
-fixed a bug when using unify + segments which share points
-performance improvements

v1.2 :
- now supports regions: use different meshing quality/detail for different areas and/or assign markers to distinguish regions. Helper module to remove region(s) included!
- option to unify the output, ie remove duplicate vertices and fix triangle indices/markers accordingly
- now supports defining single points and segments (lines) to make sure they are part of the final mesh
- option to shift the start-index per bin or to start at 0 for each bin
- new "Indices" output (due to the unify + shift indices options)
- new helpfiles and examples explaining the new features


v1.1 : 
- added boundary markers and smoothing

v1.0 : 
- initial release
   
   
   

###  known bugs:
- smoothing seems not to work in every situation, especially when using points/segments; not sure (yet) if this is due to my code or normal behaviour....
 
    
      
     
     
   
