---
uid: c24b014b-09b5-49cb-80da-6a9c602f0292
---

# World Space


![](~/img/WorldSpace3.png "")   



The coordinate system of the 3d scene is called World space (aka Model space).   

When placing a Mesh into World space it first sits with its own center at the worlds center. To position a Mesh in the scene its vertex positions are multiplied with a so called WorldMatrix. The WorldMatrix is the <span class="pin">Transform</span> of any [Effect](xref:4ae45235-b247-4d0d-8c5b-9d0688f99b3f) node.  



