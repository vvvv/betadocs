---
uid: "contribution/foscam-ip-camera-camera-control"
uid-meta: "contribution/foscam-ip-camera-camera-control-meta"
comments: 
 items: 
  - uid: "249538"
uid-files: "contribution/foscam-ip-camera-camera-control-files"
title: "FOSCAM ip camera camera control"
contribution: "true"
---

A little patch to control a FOSCAM IP camera. 
The model I have is a FI9826W. Commands may change/be supported on other camera models.

use directionnal keys to move camera or mouse if mouse control is enables.
I tried dynamically changing the speed according to the amount of mouse mouvement but the quick change of values seems to give the camera a hard time (at least on this model)

KEYS (with disabled mouse control)
ARROW -- move camera
+ / - keypad -- speed+/speed-
A/Z = zoom+/-
While mouse control : left click zoom/right click zoomout

Sorry for all the switches, could have be done in a cleaner fashion I guess, but this seems to do the trick anyway.

I might add support for cruise / preset movements / network feedback / detection later on. 
Known issue :  contrast change seems to work randomly (?)
Send to default position must be disabled to do anything else
diagonal movement is not implemented for key control but could be easily done by copying the nodes from mouse control. 

notes :
I'm not sure if there is a way to get a feedback from the camera concerning current angle/position. that would increase the possibilities.