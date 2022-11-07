---
uid: "contribution/minimum-polygon-distance"
uid-meta: "contribution/minimum-polygon-distance-meta"
uid-files: "contribution/minimum-polygon-distance-files"
title: "Minimum Polygon Distance"
contribution: "true"
---

Get minimal distance of two or more arbitrary convex polygons.
Calculation using [Rotating Calipers](http://cgm.cs.mcgill.ca/~orm/mind2p.html).

Should work with polygons of any edge point number.

Please note that:
* Polygons have to be convex
* Corner points of polygons have to be ordered clockwise
* No collision detection is performed (i.e. overlapping polygons do not have a distance of zero. Probably could use <span class="node">HitTest (2d Polygon)</span>for that.


Outputs a distance matrix containing all distances between all input polygons. Also, the closest points between the polygons are supplied.


**Not heavily tested - use with caution!**
Any feedback or suggestions for improvement is welcome.
Work partly commissioned by [This.Play](/businesses/this.play)