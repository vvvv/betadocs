---
uid: "contribution/large-ply-dx11-pointcloud-reader"
uid-meta: "contribution/large-ply-dx11-pointcloud-reader-meta"
comments: 
 items: 
  - uid: "241906"
  - uid: "241911"
  - uid: "248152"
  - uid: "273360"
  - uid: "273454"
  - uid: "273695"
  - uid: "273864"
  - uid: "273892"
  - uid: "273942"
uid-files: "contribution/large-ply-dx11-pointcloud-reader-files"
title: "Large PLY DX11 Pointcloud Reader"
image: "capture2.jpg"
contribution: "true"
---

This module goes back to this thread https://discourse.vvvv.org/t/photosynth-pointcloud-successfully-imported-to-vvvv/8559
For a long long time I was a amazed with pointclouds from lasers scaners and photosynth
A few years ago I started a company based on drone services (amdrones.com) using professional photogrametry softwares like Agisoft / Pix4d, but I wanted to port that data into V4. With a lot of help from Colorsound, davidmoraz, and everyoneishappy this module was born. Basically this 3 guys did it for me, I just made the pointcloud using pix4d and cloud compare.

The idea of this module is visualize big amount of pointclouds from a rgb,xyz file. Ply format is quite simple to understand ( if its was save in ascci, if its on binary, use cloud compare to decimate, align and export the file in ascci. It was originally made for a possible commercial project that fail, then it was on my harddrive for a few years, until node17 where I tested with HTCVIVE and its was amazing, that´s why I want to share this project so you can can give it a try.

The next step will be to save the data into a texture to feed a shader and avoid the secuencialreader,,, or maybe do the reader in VL... don´t know yet, let me know what you guys think about it.





