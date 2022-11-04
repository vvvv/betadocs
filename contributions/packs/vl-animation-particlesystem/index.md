---
uid: "contribution/vl.animation.particlesystem"
uid-meta: "contribution/vl.animation.particlesystem-meta"
comments: 
 items: 
  - uid: "273649"
  - uid: "273664"
  - uid: "273780"
  - uid: "273875"
title: "VL.Animation.ParticleSystem"
image: "thumbnail_05.jpg"
contribution: "true"
---

##  What the particle
VL.Animation.ParticleSystem is a library written in VL that deals with CPU particles.
The library allows to easily create and operate on complex particle systems.
The engine is entirely Generic, which means that every operator (and the architecture itself) is ready to be used in both 2D and 3D scenarios.
Thanks to the Entity-Component approach which the library follows, patching with it is very intuitive and descriptive.
The library is developped with vvvv gamma and the example patches work great with it, but nothing prevents you to use it as a VL plugin into your vvvv beta projects.

##  Install
VL.Animation.ParticleSystem library comes as a nuget that you can easily install in your vvvv gamma version (or VL within vvvv beta):
1. from the Quad menu (top-left)> Manage Nugets > Commandline
1. In commandline type "nuget install VL.Animation.ParticleSystem -prerelease" and press return.
1. Now the package will be available (it will also appear in the help browser when pressing F1) and you will be able to reference it from your vl document through the document menu > dependencies > VL Nugets > right click on VL.Animation.ParticleSystem entry.
1. Once referenced the library node set will be available in the node browser of VL.


##  Video documentation and tutorials
* Overview - https://discourse.vvvv.org/t/vl-animation-particlesystem-overview-1-3/17766
* Architecture in details - https://discourse.vvvv.org/t/vl-animation-particlesystem-architecture-in-details-2-3/17767
* Tutorial - https://discourse.vvvv.org/t/vl-animation-particlesystem-tutorial-3-3/17768


##  Join the development
The library is entirely opensource and you can contribute to it.   ...share your particle components!!!! :)
you can find the repository here:
<https://github.com/vvvv-dottore/VL.Animation.ParticleSystem>

Enjoy!
