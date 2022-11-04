---
uid: "contribution/text-fractal"
uid-meta: "contribution/text-fractal-meta"
comments: 
 items: 
  - uid: "70215"
  - uid: "70265"
  - uid: "70345"
uid-files: "contribution/text-fractal-files"
title: "Text Fractal"
image: "screenshot1311896457_0.png"
contribution: "true"
---

The core of this patch is a little subpatch called find_nearest. it takes a number of positions and scalings and a new position and aspect. from that it checks if the position isn't inside a rectangle and then calculates a new rectangle on that position which touches the nearest rectangle and has the given aspect.

there is also a 3d version of it, that took me years to find, but the visual output isn't as cool as i expected. but write me if you need it.