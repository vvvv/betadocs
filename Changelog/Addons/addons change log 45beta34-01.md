---
uid: a82cebda-f706-4fdc-b685-4502c2abc80d
---

# addons change log 45beta34-01
released on 21 07 15  

## new nodes
* QueueStore (Spreads): A node to store a queue of queues  
* Length (2d/3d Vector Spectral): Calculates length of a series of connected points  
* OneDollarRecognizer(2d): Plugins and modules for 2D unistroke gesture recognition as described <a href="http://depts.washington.edu/aimgroup/proj/dollar/" class="extURL" target="_blank">here</a>  
* QueryBatch (Database Network) for all database types (not just SQLite)  
* Button (3d Mesh Multitouch), Button (3d Quad Multitouch)  

## fixed nodes
* enabled WiiMote (Devices), SpaceMouse (Devices) and all the Phidget nodes in x64 build - thx to <span class="user"><a href="https://vvvv.org/users/velcrome" class="extURL" target="_blank">velcrome</a></span>  
* enabled FileStream (Irrklang) in x64 build - thx to <span class="user"><a href="https://vvvv.org/users/microdee" class="extURL" target="_blank">microdee</a></span>  
* [Connect (Spreads)](TODO INTERNALLINK:Connect (Spreads)): spreaded bin size was causing wrong output slicecount <a href="https://discourse.vvvv.org/t/connect-(spread)-bug" class="extURL forum" target="_blank">thread</a>  
* Dir (File Advanced) now correctly reports 0 with non-existing dir as input  

## changed nodes
* all Kinect (DX9) and Bullet (DX9) nodes now have a version DX9 set so they can now actually be distinguished from their DX11 counterparts  