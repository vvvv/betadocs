---
uid: b6ccc44a-e6ed-471a-ba2b-a528cade7150
---

# addons change log 45beta33.7-01
released on 21 01 15  

## new nodes
* Photoshop category, see <a href="https://vvvv.org/blog/hello-photoshop-0" class="extURL blog" target="_blank">Hello Photoshop</a>  
* TSPSDecoder (Network) module for decoding data received from: http://www.tsps.cc/  

## fixed nodes
* XDocument build up errors in HTMLTexture node weren't shown on error output pin.  
* fixed the SQLite nodes in x64 build.  
* Dialog (File Open/Save) now autoevaluate, ie. they work even with output not connected  

## changed nodes
* CameraPreview (Transform DX9) is legacy now, see the new CameraCone (EX9).  
* CreateVehicle (Bullet) new parameters for better simulation of vehicles  
* WheelInfo (Bullet Vehicle) outputs speed and skidinfo  
* Round (Value) has more options and replaces MathRound (Value)  
* more Generics for Occurrence Nodes  
* Gui2D Nodes now have an option to disable AutoSave. (no more framedrops)  
* Info (System Device) now retrieves its outputs async <a href="https://discourse.vvvv.org/t/system-info-nodes-bring-short-freezes" class="extURL forum" target="_blank">forum thread</a>