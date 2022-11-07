---
uid: "contribution/mesh-calibrator-with-multiple-cameras-for-projection-mapping"
uid-meta: "contribution/mesh-calibrator-with-multiple-cameras-for-projection-mapping-meta"
comments: 
 items: 
  - uid: "105402"
  - uid: "105493"
uid-files: "contribution/mesh-calibrator-with-multiple-cameras-for-projection-mapping-files"
title: "Mesh Calibrator with multiple cameras for Projection Mapping"
image: "PREVIEW.PNG"
contribution: "true"
---

Finally get to made the cleanup of this patch and update to last beta(I still use b27.2 !).

This is basically how we made this projection mapping:

<div class="vimeo embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe title="vimeo-player" src="https://player.vimeo.com/video/53543016" width="640" height="360" frameborder="0" allowfullscreen></iframe>
</div>


The thing I wanted to do is to have only one renderer pass, but different calibrations for each of the camera/projector, which were already 5, to keep performance cool.

I manage doing this spreading the model in 5 different objets, and spreading the camera the same way. so we have 5 mesh aligned in x with their respective camera.

This way you could edit each camera, each mesh, without affect the other cameras

Also the shader used is elliotwoods SpatialEdgeBlend which worked perfect for edge blend

EDIT: Here's the video made from dogrush studio, if you want to try it with the content of the show. You can download it from vimeo:


<div class="vimeo embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe title="vimeo-player" src="https://player.vimeo.com/video/71241408" width="640" height="360" frameborder="0" allowfullscreen></iframe>
</div>

