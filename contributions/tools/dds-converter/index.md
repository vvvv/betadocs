---
uid: "contribution/dds-converter"
uid-meta: "contribution/dds-converter-meta"
comments: 
 items: 
  - uid: "99598"
  - uid: "99599"
  - uid: "99600"
  - uid: "99601"
  - uid: "99616"
  - uid: "99710"
  - uid: "99711"
  - uid: "99716"
  - uid: "100027"
  - uid: "100029"
  - uid: "100125"
  - uid: "104164"
  - uid: "104165"
  - uid: "104166"
  - uid: "104171"
  - uid: "104174"
  - uid: "104186"
  - uid: "104214"
  - uid: "104217"
  - uid: "112471"
  - uid: "112502"
  - uid: "112518"
  - uid: "112650"
  - uid: "112696"
  - uid: "112777"
  - uid: "112780"
  - uid: "112781"
  - uid: "189515"
  - uid: "189653"
  - uid: "200080"
  - uid: "218963"
uid-files: "contribution/dds-converter-files"
title: "DDS Converter"
image: "dds_converter1.3.JPG"
contribution: "true"
---

<div class="box">
Note:
Please check also [texconvgui](xref:contribution/texconvgui) since this is much more uptodate.
</div>

Convert JPG,TGA,PNG to DDS using NVIDIA Texture Tools 2.0 with CUDA Acceleration.
Optionally resizes with Imagemagick Convert

* probably the fastest method to convert to DDS
* easier to use with this GUI
* batch convert folders (drag drop folders to app)
* CUDA Acceleration only on recent NVIDIA cards
* use NoCuda option for CPU compression on ATI / Intel chipsets

1.  Changelog
**Version 1.4**
* drag drop folders
* no cuda option added for ATI and Intel chipsets

**Version 1.3**
* now supports jpg,tga and png files
* keeps all settings
* preview first image in folder
* chessboard background for viewing images with transparency
* memory leak fixed

**Version 1.2**
* can handle filenames/paths with spaces in it
* added -fast option

**Version 1.1**

* can't handle filenames/paths with spaces in it
* full package, no installation needed, just CUDA enabled graphicscard
* Resize Pow2 automatically resizes textures to optimal power of two size
* using Lanczos interpolation see:http://www.dpreview.com/forums/thread/3125436
* Fix Filenames replaces spaces with underscores

**Notes:**
* the software is provided "as-is," without any express or implied warranty
 