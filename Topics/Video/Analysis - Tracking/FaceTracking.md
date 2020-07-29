---
uid: 03918d4f-198e-4215-bfad-67f0dfe0205b
---

# FaceTracking


#### Related nodes
FaceData (Kinect Microsoft)  
DetectObject (Freeframe DShow9)  
FaceTracker (Freeframe DShow9)  
DetectObject (CV.Image)  



These are the options vvvv offers for tracking faces. Look at their helppatches for details:  
* via Kinect: FaceData (Kinect Microsoft). Kinect1 tracks a maximum of 2 faces. Not sure about the limits of Kinect2.   
* via Freeframe:   
  * DetectObject (Freeframe DShow9) and a corresponding haarcascade file. Tracks multiple faces.  
  * FaceTracker (Freeframe DShow9)  
* via CV.Image: DetectObject (CV.Image) and a corresponding haarcascade file. Tracks multiple faces.  



