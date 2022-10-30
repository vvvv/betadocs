---
uid: "contribution/vl-opencv-pedestrian-tracker-demo"
uid-meta: "contribution/vl-opencv-pedestrian-tracker-demo-meta"
comments: 
 items: 
  - uid: "270293"
  - uid: "270573"
uid-files: "contribution/vl-opencv-pedestrian-tracker-demo-files"
title: "VL OpenCV Pedestrian Tracker Demo"
image: "2018-12-12 21-51-37.00_00_18_15.Still001.png"
contribution: "true"
---

I recently used the PedestrianDetector and Tracker nodes in a project where the tracking data was used to control a moving head light direction (more on that in another post). Got asked to give an example patch, now that it's cleaned up might just as well provide it to the vvvvhole community :)

<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/Hi-GHWK40YM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

The input is VideoIn (webcam) by default but can be switched to a VideoFile source, this gets passed through the PedestrianDetector node, results filtered by optional masks and displayed. Tracker blob/s are floating around and looking for detections to track. The trackers are set up in such a way as not to jump around too much. Further details in the patch's comments. The main output is tracker positions in pixel and dx11 space.

You can create an arbitrary amount of floating tracker blobs (depends on how much concurrent tracking your CPU can handle).

When relevant, nodes are processed asynchronously.

There are some quirks but I assume you'd be changing quite a bit to fit some production use of yours.

Here's some inspiration for a possible use of this patch:
![Dystopian tracking, XYZ project for Signal 2018](https://vvvv.org/sites/default/files/imagecache/large/images/http://files.domj.net/Tracker-Filtered.png) 
