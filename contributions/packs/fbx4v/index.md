---
uid: "contribution/fbx4v"
uid-meta: "contribution/fbx4v-meta"
comments: 
 items: 
  - uid: "240923"
  - uid: "240924"
  - uid: "240925"
  - uid: "240940"
  - uid: "240941"
  - uid: "240942"
  - uid: "240944"
  - uid: "240945"
  - uid: "240948"
  - uid: "240949"
  - uid: "240960"
  - uid: "241035"
  - uid: "241072"
  - uid: "241076"
  - uid: "241081"
  - uid: "241083"
  - uid: "241099"
  - uid: "241139"
  - uid: "241140"
  - uid: "241141"
  - uid: "241145"
  - uid: "241185"
  - uid: "243376"
  - uid: "243392"
  - uid: "243555"
  - uid: "243567"
  - uid: "250744"
  - uid: "250756"
  - uid: "250917"
  - uid: "250921"
  - uid: "250923"
  - uid: "250927"
  - uid: "251009"
  - uid: "251010"
  - uid: "251011"
  - uid: "251012"
title: "FBX4V"
contribution: "true"
---

<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/NR2CH8V4rgY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

1.  FBX4V
is an advanced FBX importer using the official Autodesk FBX SDK 2018. It might be a better choice instead of the Assimp importer if you want to use a feature specific to FBX like:
* Embedded media
* Blendshapes
* Triangulating NURBS, or higher order faces than triangles
* Using multiple UV layers
* Handling node transformation hierarchy properly
* Instantly use rigged meshes (skeletal animation) coming right from the main SkeletalMesh node
* Having a more shader oriented pipeline

##  Installation:
If you haven't already, Get [vpm](xref:contribution/vpm)
###  <a href="vpms://raw.githubusercontent.com/vvvvpm/vpdb/master/microdee/FBX4V/17.08.15.vpack">Install via vpm</a>
Read the EULA and on the bottom you'll find a toggle button for assets.
Open **girlpower.v4p** for more information ;)

##  Known issues:
Consult girlpower.v4p for known issues

##  License:
It had a non-commercial but then the whole thing broke and doesn't work. FBX4V will be merged into mp.dx soon which means it'll be under MIT license from that moment.

Enjoy!
[microdee](http://vvvv.org/users/microdee) & [Uberact](/businesses/uberact)

1.  Changelog:
##  17.08.15
* Updated to mp.dx changes
* Removed the annoyware to ease my conscience
* Added coordinate system conversion which might fix some skinning issues or might not
* Added modules to ease feeding the skeleton to SkeletalMesh
* Removed the never working Mesh module to lessen confusion
##  17.06
* Fixed vpm install script not dealing with uninitialized Pack.InstallDataFromJS
* (mp.dx/PBRIBL) Worked around nasty bug with Renderer MRT not initializing correctly inside PBRIBL in and after vvvv beta 35.5