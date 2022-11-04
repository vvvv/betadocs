---
uid: "contribution/vl.opencv-camera-calibration-helper"
uid-meta: "contribution/vl.opencv-camera-calibration-helper-meta"
comments: 
 items: 
  - uid: "277125"
  - uid: "277911"
  - uid: "277945"
  - uid: "277975"
  - uid: "277983"
uid-files: "contribution/vl.opencv-camera-calibration-helper-files"
title: "VL.OpenCV Camera Calibration Helper"
image: "calibpics.png"
contribution: "true"
---

This tool is meant to aid you in the process of generating a camera calibration file using OpenCV's xml format. The produced file contains Intrinsics information, specifically the camera matrix and the distortion coefficients. 

You can later recover this data using the IntrinsicsReader (Calibration) VL.OpenCV node.

You will need to use a calibration pattern, if you don't have one a there is a link in the patch where you can get one.

You must match your calibration pattern's columns and rows based on the INNER OUTMOUST corners in your pattern. The [pattern linked in the patch](https://docs.opencv.org/master/pattern.png) is 9x6. 

You must also measure and specify your pattern's square side length in the patch (in meters).

To be used with vvvv gamma 2020.2.2 and above.

Press 'H' while the Renderer is in focus to display additional shortcuts (britghtness, contrast, reset).

The recommendation is to try and cover as much of the edges of your sensor's field of view as possible, and to try and rotate the pattern in all three axes between the different samples. 

Getting samples at different distances is also recommended.