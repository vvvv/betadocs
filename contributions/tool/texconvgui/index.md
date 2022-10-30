---
uid: "contribution/texconvgui"
uid-meta: "contribution/texconvgui-meta"
comments: 
 items: 
  - uid: "244978"
  - uid: "245132"
  - uid: "245141"
  - uid: "245143"
  - uid: "245145"
  - uid: "271164"
  - uid: "271186"
  - uid: "271193"
  - uid: "271909"
  - uid: "271913"
  - uid: "271914"
  - uid: "271930"
  - uid: "271931"
  - uid: "271936"
  - uid: "271939"
  - uid: "271943"
  - uid: "273505"
  - uid: "273550"
  - uid: "273756"
  - uid: "273778"
  - uid: "276816"
  - uid: "276909"
  - uid: "276910"
  - uid: "276948"
  - uid: "278727"
  - uid: "278732"
  - uid: "278985"
  - uid: "279302"
  - uid: "279642"
  - uid: "279646"
  - uid: "279828"
  - uid: "279931"
  - uid: "279937"
  - uid: "279939"
  - uid: "280100"
  - uid: "280565"
  - uid: "280608"
uid-files: "contribution/texconvgui-files"
title: "TexConvGUI"
image: "TexconvGui2.0_0.png"
contribution: "true"
---

Simple GUI for [MS Texconv](https://github.com/Microsoft/DirectXTex/wiki/Texconv). 
Obviously inspired by [u7angel](http://vvvv.org/users/u7angel)'s [DDS Converter](xref:contribution/dds-converter).

Alternatives:
*[NVIDIA Texture Tools Exporter](https://developer.nvidia.com/nvidia-texture-tools-exporter)
*[Intel's Texture Works](https://gametechdev.github.io/Intel-Texture-Works-Plugin/)
*[AMD Compressonator](https://gpuopen.com/gaming-product/compressonator/)
*[PVRTexTool](https://developer.imaginationtech.com/pvrtextool/)

### v2.0-beta1 
* rebuild from scratch using vvvv and the [VL.ImGui](https://github.com/vvvv/VL.ImGui) library.
* VL.ImGui curently has problems with display scaling, added some workarounds but still looks not quite correct for settings other than 100%
* unfortunately download- and "install"-size got quite a bit fatter
* now open source
* if you encounter any problems please make an issue on [github](https://github.com/bj-rn/texconvgui)
 
### v1.3
* updated **texconv.exe** to latest (08/21), [fixes file-extensions](https://github.com/microsoft/DirectXTex/issues/170#issuecomment-890419184)
* fixed BC options, were broken due to [collapsed -bc switch](https://github.com/microsoft/DirectXTex/commit/5e8ccbf76e6336bdec642a54c8f57d42c806322f)

### v1.2
* added [OpenEXR](https://github.com/openexr/openexr) support

### v1.1
* now can deal with directories/paths that contain spaces
* updated **texconv.exe** to release *feb2019*