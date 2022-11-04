---
uid: "contribution/htmltexture-(dx11)"
uid-meta: "contribution/htmltexture-(dx11)-meta"
comments: 
 items: 
  - uid: "198974"
  - uid: "199217"
  - uid: "208726"
  - uid: "208752"
  - uid: "209022"
  - uid: "209411"
  - uid: "209783"
  - uid: "210413"
  - uid: "219725"
  - uid: "231013"
  - uid: "233340"
  - uid: "236690"
  - uid: "236692"
  - uid: "241440"
  - uid: "241946"
  - uid: "242007"
  - uid: "243292"
  - uid: "243346"
  - uid: "243389"
  - uid: "243394"
  - uid: "243395"
  - uid: "243457"
  - uid: "243534"
  - uid: "243786"
  - uid: "246378"
  - uid: "248833"
  - uid: "250425"
  - uid: "250534"
  - uid: "250717"
  - uid: "253729"
  - uid: "253921"
  - uid: "271862"
  - uid: "271864"
  - uid: "271865"
  - uid: "271870"
  - uid: "272414"
  - uid: "272416"
  - uid: "272532"
  - uid: "272540"
uid-files: "contribution/htmltexture-(dx11)-files"
title: "HTMLTexture (DX11)"
image: "icon_12.png"
contribution: "true"
---

Browser for DX11, based on ChromiumFX library. Perfectly fit for UI.

Has x64 version, support WebGL, Flash (PepperFlash), DevTools. 
If you don't need PepperFlash, you may delete this folder and browser will use system installed Flash.

##  Components
* CEF 3.2454.1323 / 3.2454.1317 (x64)
* PepperFlash 19.0.0.201
* LivePage 1.6.1 

###  Advantages
* Use modern CEF version,
* JavaScript callbacks through global object (and its functions) or global function,
* LivePage extension,
* Popup and URL filters,
* Custom User-Agent string,
* Keyboard and mouse simulating through hidden pins

###  Warning & Restrictions
Browser is very hungry for application memory (for that case using x64 version is required)
Some proprietary codecs (mp3, mp4, aac) not supported

Submit bugs and requests to:
https://github.com/gumilastik/VVVV.HTMLTexture.DX11

Latest Sources at:
https://github.com/tebjan/VVVV.HTMLTexture.DX11

