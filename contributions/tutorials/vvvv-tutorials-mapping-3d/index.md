---
uid: "contribution/vvvv.tutorials.mapping.3d"
uid-meta: "contribution/vvvv.tutorials.mapping.3d-meta"
comments: 
 items: 
  - uid: "83103"
  - uid: "83106"
  - uid: "83109"
  - uid: "83115"
  - uid: "83123"
  - uid: "83127"
  - uid: "83130"
  - uid: "83131"
  - uid: "83132"
  - uid: "83140"
  - uid: "83141"
  - uid: "83226"
  - uid: "83257"
  - uid: "83532"
  - uid: "83655"
  - uid: "83664"
  - uid: "84638"
  - uid: "84991"
  - uid: "85072"
  - uid: "85163"
  - uid: "85343"
  - uid: "87305"
  - uid: "87423"
  - uid: "87466"
  - uid: "87766"
  - uid: "90157"
  - uid: "90175"
  - uid: "96096"
  - uid: "97565"
  - uid: "99099"
  - uid: "99113"
  - uid: "100749"
  - uid: "101972"
  - uid: "102025"
  - uid: "102643"
  - uid: "102738"
  - uid: "102975"
  - uid: "103048"
  - uid: "104478"
  - uid: "104622"
  - uid: "104623"
  - uid: "104970"
  - uid: "104983"
  - uid: "111292"
  - uid: "111308"
  - uid: "111320"
  - uid: "111321"
  - uid: "111324"
  - uid: "113366"
  - uid: "113389"
  - uid: "113431"
  - uid: "113446"
  - uid: "152140"
  - uid: "153664"
  - uid: "153799"
  - uid: "154360"
  - uid: "158269"
  - uid: "160244"
  - uid: "160262"
  - uid: "165499"
  - uid: "165754"
  - uid: "166159"
  - uid: "181751"
  - uid: "185255"
  - uid: "212690"
  - uid: "222113"
  - uid: "275162"
  - uid: "275165"
  - uid: "275168"
uid-files: "contribution/vvvv.tutorials.mapping.3d-files"
title: "VVVV.Tutorials.Mapping.3D"
image: "projection.node_.PNG"
contribution: "true"
---

Tutorial on 3D projection mapping using the CalibrateProjector node (wrapping OpenCV's CalibrateCamera routine).

1.  Quickstart guide:

##  Downloads

## [VVVV 27.2 or above](https://vvvv.org/downloads)
## [opencv-plugin-(alpha)](xref:contribution/opencv-plugin-(alpha))
## Tutorial files (in download link at bottom of description)

##  <iframe width="560" height="315" data-src="https://www.youtube

<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/0Pw-dPyke4s" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
<iframe width="560" height="315" data-src="https://www.youtube
##  Walkthrough

<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/BmQMSzNRoKk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


1.  Detailed instructions

##  Scan object in Reconstructme

##  Convert .3ds to .x file

##  Controls to add / modify points in world points

Use your mouse in the World renderer to move control points to features on the mesh (virtual object).

| | |
|---|---|
Enter | Add new point
Backspace | Delete point
Tab | Select next point
Shift+Tab | Select last point


##  Controls to modify points in projector space

Use your mouse in the world renderer to drag the control points coming out of the projector onto the corresponding features of the real object.
| | |
|---|---|
Space | Reset point to world view camera
Tab | Select next point
Shift+Tab | Select last point


##  Export matrices

Use the SaveViewProjection node at the bottom of the patch to save the View and Projection matrices (i.e. the result of the calibration process). These can then be loaded into other patches with the LoadViewProjection node (packaged in the download).


1.  Introduction to 3D projection mapping

##  3D projection mapping

What I'd describe as '3D projection mapping' is the act of re-projecting a virtual 3D object onto its real world counterpart using a video projector*. Thereby all of the features of the real object which are visible from the point of view of the projector have an image projected onto them, and this image is 'extracted' from the corresponding surfaces of the virtual counterpart object.

*\* thereby defining '2D projection mapping' as lining up 2D shapes in a projector image with real world features in the projector's line of sight.*

##  The camera model

A projector has the same optical properties as a camera, whereby a scene in 3D is projected onto a plane in 2D (camera) or an image from a plane in 2D projected onto a 3D scene (projector). This comes from the Principle of Reversibility, whereby in optics reversing any path of light results in a valid system. 

###  Film example

Imagine a film camera on a tripod in front of a table which is covered in objects. When we take a photo, light hits the objects and is scattered, rays that are scattered directly towards the camera's aperture are captured on the film. Each minute section of the film is looking through the aperture at one part of the scene, and therefore captures light from that part of the scene only. 

Presume we don't move the film at all, it stays in the camera as it was when we took the photo. If we then develop the film inside the camera, then the image of the scene will appear on the film. If we open the aperture now, each section of the film is still looking through the aperture at its corresponding section of the scene. Imagine we shine light onto the film so that the film is bright, it is scattering light from each section of the film based on the intensity pattern of the image. This light then travels back through the aperture and will hit the section of the scene corresponding to each part of the image. The image of the scene will be 'projection mapped' back onto the scene (or perhaps the negative image).

###  Virtual camera

In the film example, the 'projector' and camera conveniently share the exact same optics:

* The position and rotation relative to the scene (pose)
* The lens, size of film and distance between lens and film (relative focal length)
* The planar offset of the film with respect to the lens (lens offset)
* The barrel distortion of the lens (lens distortion)

If we want to match a virtual camera with a real video projector, then we must create a camera that shares all these above properties with the projector.

Conveniently, the standard model of a video projector is to have no lens distortion (i.e. if you shine the image onto a flat surface, you will always get a rectangular image). Therefore we omit this property, and can very effectively define a projector with standard computer graphics camera matrices (view and projection matrices).

The remaining properties can be categorised into 2 sets:
| | | |
|---|---|---|
Extrinsics | World Transform | Translation <3>, Rotation <3>
Intrinsics | Projection Transform | Focal length (XY) <2>, Lens offset (XY) <2>


This gives us 10 degrees of freedom for our virtual camera. 

##  Aligning a camera model

We can either enter these 10 parameters (above) manually as in [HowTo Project On 3D Geometry](xref:e270f10f-568b-4fc3-83ba-8315208e0e8d), or we could find a mechanism that will calculate these for us.

The previous automatic route for this was Pade projection mapping (which required a custom vertex shader). This CalibrateProjector uses OpenCV's CalirateCamera function in order to perform this automatic solving for us, and provides standard View and Projection matrices.

The general benefit of the automatic route is that it allows a more immediate interaction between the person calibrating and the result that they want to achieve. By manipulating control points on the mesh and in the projector, the operator can more quickly and confidently achieve an accurate mapping, and fine tune the mapping by adding extra control points in problem areas, without compromising the existing data entered.


1.  Further references

1. Notes on 3D mapping in VVVV : [HowTo Project On 3D Geometry](xref:e270f10f-568b-4fc3-83ba-8315208e0e8d)
1. Kyle McDonald's Mapamok : <https://github.com/YCAMInterlab/ProCamToolkit/wiki/mapamok-(English)>
1. Workshop files for 'Projecting on the things' workshop at Node 10 : <http://workshops.vvvv.org/-ProjectingOnThings/>


1.  Watch out for:

<div class="box">
Note:
##  World window selects points at back

**This can happen if your graphics card doesn't have the same depth buffer settings available as mine**
If you encounter a problem selecting points in the World view where:
When you select a points on the front of an object, the patch instead selects a point on the back of the object, then try the following:

* Open Mesh.SelectPoints (1/3 way down calibrate.v4p on left hand side)
* Open Intersect (1/5 way down Mesh.SelectPoints.v4p on left hand side)
* Select the Renderer (EX9) in the patch (the box in the middle)
* Open Herr Inspektor (Ctrl+I)
* Check that the 'Windowed Depthbuffer Format' is not set to 'None', e.g. set it to 'D16'
</div>