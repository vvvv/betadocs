---
uid: "contribution/calibrate-and-re-project"
uid-meta: "contribution/calibrate-and-re-project-meta"
comments: 
 items: 
  - uid: "265848"
  - uid: "266216"
  - uid: "266617"
  - uid: "271092"
uid-files: "contribution/calibrate-and-re-project-files"
title: "Calibrate and Re-Project"
image: "vvvv-Calibrate-and-Re-Project-Contribution2.png"
contribution: "true"
---

Semi-automatically calibrate your projector and throw generated content on to your physical object. These are convenience patches providing a simple workflow for using the projector-calibration that is coming with the ImagePack.

It was presented at [Mapping Festival](/blog/vvvv-at-mapping-festival-2016), [Gray Area Festival](/blog/vvvv-workshop-at-gray-area) and [CGEvent](/blog/vvvv-at-cg-event-2016) in 2016.

Two Patches are explaining the techniques and show how to use the modules:

* Step01_CalibrateProjector.v4p
* Step02_ReProjectionSetup.v4p

#### Projector Calibration
1. Place your projector anywhere and point it to a physical object (your "screen") you want to project on to.
1. Measure several physical points on your "screen" and type their positions into the patch.
1. Match the points in the projection to the measured points with a few simple clicks.
1. Hit 'Solve' to get the View/Projection matrices needed for the Renderer.

#### Re-Projection
1. Create a 3d Content and render it from the spectator's point of view.
1. Project. For more about this projection mapping technique, see: [Projection Mapping Primer](xref:d09ac451-f613-447d-afaa-5a32cdc1ce8c).

#### Requirements
* [vvvv Alpha](https://vvvv.org/downloads/previews) from 35.3 onward.
* [ImagePack](/contribution/vvvv.packs.image) is used by the projection calibration module.

#### Known issues
**ATI cards**
There is a known problem with the ImagePack and Radeon graphic cards. 
The solution was proposed by [tekcor](http://vvvv.org/users/tekcor):
1. Download "nvcuda.dll":  <http://www.symbioticcube.com/Downloads/nvcuda.dll>
1. Place it in your ImagePack's *nodes/plugins/dependencies/opencv/x86/* folder. 
At the moment only 32bit version of the pack is working on my ATI machine.

![](https://vvvv.org/sites/default/files/imagecache/large/images/Contribution-FoldableModel-by-Emarao.png) 
*Foldable model by Emarao based on A4 dimensions*