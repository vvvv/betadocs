---
uid: "contribution/cooktorrancemultitexfresnel"
uid-meta: "contribution/cooktorrancemultitexfresnel-meta"
uid-files: "contribution/cooktorrancemultitexfresnel-files"
title: "CookTorranceMultiTexFresnel"
image: "CookTorranceMultiTexFresnel Thumbnail.jpg"
contribution: "true"
---

Shading via multitexture. Two textures are interpolated over the surface, and their product results in the final specular BDRF.
The initial textures supplied approximate a Cook-Torrance model using one set of possible parameters, but different textures can be used to emulate a wide variety of isotropic BRDF models.
In this example lambertian diffuse is still supplied, but it is not required.