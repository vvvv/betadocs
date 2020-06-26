# World Space


![](~/img/WorldSpace3.png "")   



The coordinate system of the 3d scene is called World space (aka Model space).   

When placing a Mesh into World space it first sits with its own center at the worlds center. To position a Mesh in the scene its vertex positions are multiplied with a so called WorldMatrix. The WorldMatrix is the <span class="pin">Transform</span> of any [Effect](TODO INTERNALLINK:Shader) node.  



