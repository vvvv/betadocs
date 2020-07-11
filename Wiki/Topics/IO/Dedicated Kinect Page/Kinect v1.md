---
uid: 96af9665-1d88-4d4e-b8d0-e1e50a6eb2bc
---

# Kinect v1

![](~/img/300px-Xbox-360-Kinect-Standalone.png "")   

Nodes for using the original <a href="http://en.wikipedia.org/wiki/Kinect" class="extURL" target="_blank">Kinect</a> are shipping with vvvvs addonpack.  

With the addonpack installed type *kinect* in the [nodebrowser](TODO INTERNALLINK:nodelist) to see a list of all available nodes dealing with it. Note that most nodes come in two versions:  
* Microsoft  
* OpenNI  
Those relate to two different drivers they are based on. Depending on which version you want to use you need to install the following:  

## Microsoft
The Microsoft Kinect nodes by <span class="user"><a href="https://vvvv.org/users/vux" class="extURL" target="_blank">vux</a></span> require you to install the <a href="http://www.microsoft.com/en-us/download/details.aspx?id=40277" class="extURL" target="_blank">Kinect for Windows Runtime v1.8</a>.  

If the <span class="node">Kinect (Devices Microsoft)</span>'s <span class="pin">Kinect Status</span> tells you that *the device is not genuine* you may have either of two problems:  
* the date is not set correctly on your PC (!)  
* you are using a "Kinect for XBox" in which case you need the  <a href="https://www.microsoft.com/en-us/download/details.aspx?id=40278" class="extURL" target="_blank">Kinect SDK</a> installed (as those are not allowed to be used on windows PC for end-usage, but development only).  

## OpenNI
The OpenNI Kinect nodes are now considered legacy since the drivers are no longer being developed any further. In case you still need them, here is what you need to get them running:  
* get <a href="http://reconstructme.net/?wpdmdl=26" class="extURL" target="_blank">OpenNI Sensor Driver Package x86 1.5.2.zip</a> as comfortably provided by <a href="http://reconstructme.net" class="extURL" target="_blank">http://reconstructme.net</a> 
* from that .zip install: OpenNI-win32-1.5.2.23-redist.msi  
* now depending on your hardware install either:  
  * **Asus Xtion**: SensorPrimesense-win32-5.1.0.41-redist.msi  
  * **Kinect**: SensorKinect-Bin-Win32-v5.1.0.25.msi  
* also get <a href="http://www.openni.org/wp-content/uploads/2012/12/NITE-Win32-1.5.2.21-Dev.zip" class="extURL" target="_blank">NITE 1.5.2.21</a> and install it  

The current version of the OpenNI plugins was tested to run with:  
* OpenNI 1.5.2.23 (32bit, stable, redist edition)  
* NITE 1.5.2.21 (32bit, stable, redist edition)  
* SensorKinect091 5.1.0.25 (32bit)  

These are also the drivers needed to use the kinect nodes that come with the <a href="https://vvvv.org/contribution/vvvv.packs.image" class="extURL contribution" target="_blank">Image Pack</a> by <span class="user"><a href="https://vvvv.org/users/elliotwoods" class="extURL" target="_blank">elliotwoods</a></span>  

note:  
If for some reason you need to have both Microsoft & OpenNI drivers installed check out <a href="http://code.google.com/p/kinect-mssdk-openni-bridge/" class="extURL" target="_blank">kinect-mssdk-openni-bridge</a>  
  

## Skeletal Data
The following graphic shows the skeletal joints the kinect returns. Below are the joints names next to their slice index as they are returned by <span class="node">Skeleton (Kinect Microsoft)</span>  



![](~/img/http://www.codeproject.com/KB/dotnet/KinectGettingStarted/7.png "")   


 0  HipCenter
 1  Spine
 2  ShoulderCenter
 3  Head
 4  ShoulderLeft
 5  ElbowLeft
 6  WristLeft
 7  HandLeft
 8  ShoulderRight
 9  ElbowRight
 10 WristRight
 11 HandRight
 12 HipLeft
 13 KneeLeft
 14 AnkleLeft
 15 FootLeft
 16 HipRight
 17 KneeRight
 18 AnkleRight
 19 FootRight
