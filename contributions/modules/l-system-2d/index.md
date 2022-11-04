---
uid: "contribution/l-system-2d"
uid-meta: "contribution/l-system-2d-meta"
uid-files: "contribution/l-system-2d-files"
title: "L-System 2D"
image: "lsystem2.jpg"
contribution: "true"
---

Let's create cool generative art.

##  How to use
This L-System grammer is similar to lsys ( <http://benvan.co.uk/lsys/> ).
~np~
F     : draw forwards by "size"
+ / - : rotate by +/-"angle"
> / < : increase/decrease "size" by "DeltaSize"
) / ( : increase/decrease "angle" by "DeltaAngle"
<%20/%20> : push / pop state
1.      : negate "angle"
|     : increment "angle" by 180(degree)
~/np~

##  Advice
This is a beta version.
When you write a deeply recursived expression, the behavior may be slow.
I wanna increase the performance.
