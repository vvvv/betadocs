---
uid: "contribution/tracker"
uid-meta: "contribution/tracker-meta"
comments: 
 items: 
  - uid: "236896"
uid-files: "contribution/tracker-files"
title: "Tracker"
image: "crosshair.png"
contribution: "true"
---

This is a simple Tracker. It can be used to stabilize blobs, handle ghost blobs and smooth the incoming data a bit. If you ever stumbled over common problems like discussed [damper-issues-when-spread-count-changes" "here](https://discourse.vvvv.org/t/damper-issues-when-spread-count-changes" "here), you'll find this probably useful.

The plugin comes in 2 flavours which depend on your usecase:
####  Tracker (ID)
* when you use a tracking system that provides reliable IDs (like a fiducial tracking)
####  Tracker (Size)
* when you use a tracking that doesn't provide an ID but gives you rectangles for each blob (like detectObject)
* the size of those rectangles is then used to find lost blobs again.

Both of them can (and must be) easily modified for other usecases... think 3d blobs or a different criteria should be used for similarity detection.

That whole thing started by recreating [Daniel Shiffmans Tutorial](http://shiffman.net/general/2011/04/26/opencv-matching-faces-over-time/) which was then extended with different features.