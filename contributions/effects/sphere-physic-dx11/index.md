---
uid: "contribution/sphere-physic-dx11"
uid-meta: "contribution/sphere-physic-dx11-meta"
comments: 
 items: 
  - uid: "220965"
  - uid: "221166"
uid-files: "contribution/sphere-physic-dx11-files"
title: "Sphere physic Dx11"
image: "root-Renderer_2014.08.15-02.54.57.png"
contribution: "true"
---

Basic physic engine with static and dynamic sphere, ported from here http://stackoverflow.com/questions/345838/ball-to-ball-collision-detection-and-handling 
you can't really stack sphere as they become instable , also if the sphere move to fast the collision might be miss... both of this might be fix by using continuous collision detection   and finnally note that the sphere are not rotating...
You can actually get the colliding sphere id back with readback from buffer... 