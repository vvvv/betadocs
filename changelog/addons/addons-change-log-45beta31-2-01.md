---
uid: 24e365b0-0577-445a-8fbf-7ff79fb935ee
---

# addons change log 45beta31.2-01
released on 11 11 13  

## fixed nodes
* Fixed mesh not updating issue in Metaballs (EX9.Geometry) when connected to more than one device  
* HTMLTexture (EX9.Texture)  
  * Fixed blend mode in help patch  
  * Fixed <a href="https://discourse.vvvv.org/t/htmltexture-node-does-not-update-current-url-pin" class="extURL forum" target="_blank">htmltexture-node-does-not-update-current-url-pin</a>  
  * Fixed keyboard events  
* Disperse (Spreads) a lot faster  

## changed nodes
* TUIODecoder (Network 1.0) now with correct 'Session ID', 'Class ID' and 'Type' outputs (old one is legacy)  
* added 'database' tag to all database nodes (for convenience)  
* Select ({database} Network) now trims whitespace of given comma-separated <span class="pin">Field Names</span>  
* Directory (File) deletes non empty dirs as well  

## new nodes
* Stickman (Kinect EX9)  
* SkeletonJoints (Kinect OpenNI)  

## new girlpowers
* Arduino Firmata demos by <span class="user"><a href="https://vvvv.org/users/jens.a.e" class="extURL" target="_blank">jens.a.e</a></span>