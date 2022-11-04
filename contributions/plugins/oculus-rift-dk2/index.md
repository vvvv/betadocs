---
uid: "contribution/oculus-rift-dk2-0"
uid-meta: "contribution/oculus-rift-dk2-0-meta"
comments: 
 items: 
  - uid: "193071"
  - uid: "193155"
  - uid: "193460"
  - uid: "193530"
  - uid: "193532"
  - uid: "193895"
  - uid: "194119"
  - uid: "194120"
  - uid: "202400"
  - uid: "204196"
  - uid: "220586"
  - uid: "220590"
  - uid: "220629"
  - uid: "220873"
uid-files: "contribution/oculus-rift-dk2-0-files"
title: "Oculus Rift DK2"
image: "Oculus (Oculus Wrap).png"
contribution: "true"
---

<div class="box">
Note:
These nodes might be outdated, use [VVVV.OpenVR](xref:contribution/vvvv.openvr) for VR related projects. 
</div>

Oculus Rift Plugin, extended desktop vvvv rendering only, NO DIRECTMODE, no timewarp, but uses correct distortion parameters via meshes and generally works. Might work for DK1.

Probably only works with Oculus version 0.4.4.

Works better in 64bit than 32.

Make Oculus Renderer the main Display with 75Hz and Output is smooth.

If Rift is secondary display you can try setting your main display to 75Hz. But still they are not synced so experience is not as good.

Based on OculusWrap a very nice .NET Wrapper for the Oculus Rift SDK:
<https://oculuswrap.codeplex.com/>