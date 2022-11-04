---
uid: "contribution/vl.dbscan"
uid-meta: "contribution/vl.dbscan-meta"
comments: 
 items: 
  - uid: "273865"
uid-files: "contribution/vl.dbscan-files"
title: "VL.DBSCAN"
image: "vl_dbscan_icon.png"
contribution: "true"
---

This plugin provides an implementation of the DBSCAN algorithm for VL, based on [viceroypenguin's C# lib](https://github.com/viceroypenguin/DBSCAN). It allows you to track clusters of points inside a 2D pointcloud. 

It can be useful if you're using a LIDAR to track people in a room, or hands on a wall.

To install, go to VL's command line and type

```
nuget install VL.DBSCAN
```

An example patch is provided with the package. Also, you can find the source of this plugin [here](https://github.com/sebescudie/VL.DBSCAN).

Enjoy, and if something goes wrong please shout!

**UPDATE :** The plugin now uses Xenko Maths, and its help patch is available in the help browser.

seb