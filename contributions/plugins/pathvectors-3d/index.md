---
uid: "contribution/pathvectors-(3d)"
uid-meta: "contribution/pathvectors-(3d)-meta"
comments: 
 items: 
  - uid: "105680"
  - uid: "105689"
  - uid: "105710"
  - uid: "105711"
  - uid: "105811"
  - uid: "105834"
  - uid: "105867"
  - uid: "111046"
  - uid: "151664"
  - uid: "216026"
  - uid: "216548"
  - uid: "233577"
  - uid: "233579"
  - uid: "233580"
  - uid: "233582"
uid-files: "contribution/pathvectors-(3d)-files"
title: "PathVectors (3d)"
image: "screenshot02-09-2013 01.47.35_0.png"
contribution: "true"
---

Some of you might know the [ArcLength](xref:contribution/arclength(3d-generic)) module. It's very nice because it's able to place points at specified distances along a spline.

Unfortunately, it's not spreadable (some of the nodes needed for this don't have general purpose, use- and meaningful spreadable implementations).

Thus here I present to you PathVectors (3d), rewritten as plugin, spreadable, binsizeable and fast.

You basically input a spread of splines and a spread of percentages at which to place new points. See the help patch for different usecases.