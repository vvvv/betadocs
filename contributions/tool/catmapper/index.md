---
uid: "contribution/catmapper"
uid-meta: "contribution/catmapper-meta"
comments: 
 items: 
  - uid: "101668"
  - uid: "101672"
  - uid: "102243"
  - uid: "102246"
  - uid: "102252"
  - uid: "102260"
uid-files: "contribution/catmapper-files"
title: "CatMapper"
image: "3D_Homography-MasterEditor_2013.05.31-15.44.41.png"
contribution: "true"
---

This is a basic patch for doing 3D mapping using 3d Homography.
The idea is that you choose 4 points on your 3d model, and then match them to the real world, once done those points become fixed, and you move your projector until the perspective matches the rest of the scene. Its pretty quick to settup as long as your model is accurate.
Has a basic multiple coloured softshadows implimentation. 
The model is from a very quick mapping I did a few years ago (that how long this patch has been kicking around before tidying!)

Please if you make use of this patch, please include any updates you might make into the contrbution, it would nice to have a remixed mapping patch!
I have had it working with Elliots camera calibration plugins, but they are a bit flaky execept in a specific build of vvvv that he has, hopefully that will be fixed soon...
Let me know if it works for you

Cat