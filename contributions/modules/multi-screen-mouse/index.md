---
uid: "contribution/multi-screen-mouse"
uid-meta: "contribution/multi-screen-mouse-meta"
comments: 
 items: 
  - uid: "243277"
uid-files: "contribution/multi-screen-mouse-files"
title: "Multi Screen Mouse"
image: "MultiScreenMouse_0.png"
contribution: "true"
---

It's a pretty simple patch, but useful. If you use more than one screen, select the screen you want and the module will map your mouse coordinates to (-1;1) on that screen. Note that it will also map correctly if you have just one screen.

Neighboring screens will be outside of (-1;1).

(I was surprised to find that there was nothing like this available already.)

/edit 30.09.2010: small bugfix