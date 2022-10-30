---
uid: "contribution/engravvvver"
uid-meta: "contribution/engravvvver-meta"
uid-files: "contribution/engravvvver-files"
title: "Engravvvver"
image: "engravvvved.jpg"
contribution: "true"
---

## Engravvvver GCode Generator
The Engravvvver is a vvvv patch that reads a pixel image (.BMP / .JPG / .PNG / etc) 
and converts it into a machine-readable GCode path for 2D raster engraving. Every GCode is saved incrementally within the folder of the source image.

**You can**

*   set the laser power (min/max) from 0-255
*   set the travel and feed rate
*   set the scan resolution (pixel size in mm),
*   define a cutout shape (quad/circle) as well as cutout speed and power
*   see the graphical representation of the gcode line that is currently being written
* generate GCode files (yay!), these can be quite large!!

**You can not**
*   achieve a higher feed rate than the max amount of gcode lines per second that your machine can receive
*   send the gcode "on-the-fly" to a device (I use Universal GCode Sender **2.0**  <https://github.com/winder/Universal-G-Code-Sender>) 

