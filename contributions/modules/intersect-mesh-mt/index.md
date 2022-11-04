---
uid: "contribution/intersect-(mesh-mt)"
uid-meta: "contribution/intersect-(mesh-mt)-meta"
uid-files: "contribution/intersect-(mesh-mt)-files"
title: "Intersect (Mesh MT)"
image: "1.PNG"
contribution: "true"
---

This module allows the use of Intersect (3d mesh ray) with a spread of values without a great deal of performance overhead. Raycasts are only performed when a new x/y slice is given to the module.

The module returns the closest xyz point (to the camera) for all the meshes a ray intersects with. It also takes a 'max hits' constant as input and uses this to create a buffer containing the indices of each object/mesh a ray intersects with. Also returned from the module, are a boolean list to show which rays are intersecting with meshes (1 for any intersection, 0 for no intersections), and a list to show how many objects each ray intersects with.

The help patch shows one way this information can be used to interact with a set of objects.