---
uid: "contribution/obsolete-arclength(3d-generic)"
uid-meta: "contribution/obsolete-arclength(3d-generic)-meta"
comments: 
 items: 
  - uid: "55107"
  - uid: "57685"
  - uid: "79763"
  - uid: "93987"
  - uid: "100618"
  - uid: "104596"
  - uid: "105651"
  - uid: "105662"
uid-files: "contribution/obsolete-arclength(3d-generic)-files"
title: "[OBSOLETE] ArcLength(3d generic)"
image: "ArcLength(3d generic) example output.jpg"
contribution: "true"
---

ArcLength(3d generic)takes a spread of 3D co-ordinates and calculates the length of the straight lines connecting them from start to finish.
Another pin will take a spread of lengths from which the module will output a spread of coordinates, and the slice number of the nearest input point.
Note that the slice number returned is a decimal. this means that if the slice number 3.49 is returned and you use it with a getslice node, getslice will return slice 3, if the slice number is 3.51 slice 4 will be returned, in this way the closest point is determined.
If a length specified is between two original helper points then the output point is calculated to lie somewhere along the straight line between the two points.
Obviously the higher the spread count of helper points the more accurate this will be.
Dont forget to specify if the curve is open or closed!
Useful for any spread whether it is bezier based, b-spine based or any list of 3d coordinates meant to represent a line in 1,2, or 3D space.
Helper points are input as an (xyz) vector so to calculate for only 2d or 1d set the unused coordinates to 0 in a <span class="node">Vector (3d Join)</span>.

main nodes used are <span class="node">Integrate </span>and <span class="node">Interval</span> and <span class="node">Normalise</span>
Bins are yet to be implemented (feel free to so !)
Enjoy
john
[john](http://vvvv.org/users/john)
