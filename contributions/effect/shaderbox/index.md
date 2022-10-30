---
uid: "contribution/shaderbox"
uid-meta: "contribution/shaderbox-meta"
comments: 
 items: 
  - uid: "261719"
  - uid: "261737"
  - uid: "271492"
  - uid: "271854"
uid-files: "contribution/shaderbox-files"
title: "Shaderbox"
image: "HowToWriteYourOwnShaderbox-Renderer_2018.08.12-23.40.17.png"
contribution: "true"
---

This is a bunch of DX11 effects that let you use [shadertoys](https://www.shadertoy.com) as skyboxes. I've borrowed the idea of doing this from Bradley Austin's book Oculus Rift in Action and decided to use it into the vvvv environment. 
## Background 
[Shadertoys](https://www.shadertoy.com) were always magical things for me. There is infinite beauty in ability to build entire world with pure maths, using fractals, distance functions, raytracing and all the staff. The result can totally blows ones mind. But the problem is that shadertoy is a pixel shader. In three dimensional space it is represented as a quad with 2d texture. It reminds a window to another realm. You can't put a 3d model inside or use vvvv cameras to rotate the view.
## What's in it
Shaderboxes allows you to immerse in shaders. This contribution contains some effects, witch you can use to wrap whole 3d scenes in shadertoys.

![title](https://vvvv.org/sites/default/files/imagecache/large/images/https://media.giphy.com/media/1xp0Amfwnw1jijzoeL/giphy-downsized-large.gif)
## DIY 
Besides a couple of converted shaders there is a small **HowTo** patch in /girlpower folder, that explains how to convert one particular shadertoy to skybox.
## Dependences 
*Make sure you have DX11 pack 
## Practical use 
I've created the contribution to play with it. Initially my main intention was to be able to travel through fractals in VR glasses, but I see more practical usage in creation of procedural skyboxes of all kinds.