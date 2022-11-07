---
uid: "contribution/smooth-per-vertex-normals"
uid-meta: "contribution/smooth-per-vertex-normals-meta"
comments: 
 items: 
  - uid: "190181"
uid-files: "contribution/smooth-per-vertex-normals-files"
title: "Smooth Per Vertex Normals"
image: "Smooth.png"
contribution: "true"
---

It's based on calculating the adjacent faces of each vertex on the CPU in a dynamic plugin. As long as the typology of the mesh doesn't change this works fine.
This data is then used to apply the previously calculated face-normals.

I'm sure this can be greatly improved, so any comments and suggestions welcome.

Still missing is a weighting of the normals like in this example:
http://www.bytehazard.com/articles/vertnorm.html

Based on GSFX Per vertex normals by lasal.