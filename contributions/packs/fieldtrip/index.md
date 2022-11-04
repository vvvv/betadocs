---
uid: "contribution/fieldtrip"
uid-meta: "contribution/fieldtrip-meta"
comments: 
 items: 
  - uid: "248069"
  - uid: "248070"
  - uid: "248099"
  - uid: "248101"
  - uid: "248128"
  - uid: "248155"
  - uid: "248162"
  - uid: "248163"
  - uid: "248165"
  - uid: "248299"
  - uid: "248813"
  - uid: "248819"
  - uid: "256727"
  - uid: "257342"
  - uid: "276825"
  - uid: "276832"
uid-files: "contribution/fieldtrip-files"
title: "FieldTrip"
image: "1895-ill3-1024x586.jpg"
contribution: "true"
---

vvvv pack for working with 2D and 3D scalar and vector fields.

Please check FieldTrip\girlpower\FieldGuide for an overview, and  FieldTrip\girlpower\FieldSpecimens for some curious examples.

Some highlights:

•	modular node based raymarching 

•	lots of 2D & 3D SDFs (signed distance fields)

•	lots of useful noise functions

•	texture baker (handy if you want to for example use 3D noise in existing shaders)

•	some nice higher order tricks like being able to derive the gradient or curl of a function, Euler, RK2 & RK4 integration of a function

•	DX11.Particles pack adapter

•	SuperPhysical pack Raymarcher


Requires: 

  •vvvv >= 35.7 + Addon Pack
  
  •DX11 pack >= 1.1
  
  •[happy.fxh](xref:contribution/happy.fxh)  <https://github.com/everyoneishappy/happy.fxh>
  
  •[instance-noodles](xref:contribution/instance-noodles)  <https://github.com/everoneishappy/InstanceNoodles>
  
  •a GPU that supports Shader Model 5

To install everything via VPM: https://vvvvpm.github.io/#FieldTrip
To install manually just place in /packs folder.  
For more frequent updates, bug fixes and issue reporting: https://github.com/everyoneishappy/FieldTrip



MIT License- feel free to use in your creative & commercial projects.  If used in production a credit is very appreciated:

Kyle McLean / <http://everyoneishappy.com>

I’m also very happy if you are doing something interesting and want to employ me on a project basis.