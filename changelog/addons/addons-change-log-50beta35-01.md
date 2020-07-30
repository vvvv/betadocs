---
uid: 20808fea-dc88-4f49-9beb-7378cc12a2d6
---

# addons change log 50beta35-01
released on 20 12 16  

### New
* new MJpegStream (EX9.Texture Sender/Receiver) modules  
* new module for concave polygons Polygon (EX9.Geometry 2d Concave)  

### Fixes
* MESO has sponsored an <a href="https://vvvv.org/blog/htmltexture-update-to-chromium-54" class="extURL blog" target="_blank">update of the HTMLTexture nodes</a>  
* Two new pins on AudioOut node, to allow lower latency settings when needed.   
* Arduino (Devices StandardFirmata 2.x) and  FirmataDecode (Devices 2.x) return proper strings  
* fixed MakePath troubles with root volume paths without trailing slash, fixed nil output on any nil input  
* fixed crash with invalid searchPatterns for Dir (File Advanced)