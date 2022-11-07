---
uid: "contribution/directx-freeframegl-bridge"
uid-meta: "contribution/directx-freeframegl-bridge-meta"
comments: 
 items: 
  - uid: "100157"
  - uid: "100159"
  - uid: "100160"
  - uid: "100161"
  - uid: "100162"
  - uid: "100163"
  - uid: "100165"
  - uid: "100166"
  - uid: "100167"
  - uid: "100168"
  - uid: "100174"
  - uid: "100178"
  - uid: "100179"
  - uid: "100181"
  - uid: "100186"
  - uid: "100187"
  - uid: "100190"
  - uid: "100220"
  - uid: "100229"
  - uid: "100231"
  - uid: "100232"
  - uid: "100237"
  - uid: "100239"
  - uid: "100243"
  - uid: "100244"
  - uid: "100245"
  - uid: "100249"
  - uid: "100266"
  - uid: "100283"
  - uid: "100295"
  - uid: "100313"
  - uid: "100315"
  - uid: "100390"
  - uid: "100391"
  - uid: "100394"
  - uid: "100399"
  - uid: "100415"
  - uid: "100422"
  - uid: "100449"
  - uid: "100468"
  - uid: "100505"
  - uid: "100509"
  - uid: "100685"
  - uid: "100705"
  - uid: "100732"
  - uid: "100743"
  - uid: "100763"
  - uid: "100791"
  - uid: "100844"
  - uid: "100846"
  - uid: "100887"
  - uid: "100888"
  - uid: "100889"
  - uid: "100890"
  - uid: "100916"
  - uid: "101029"
  - uid: "101041"
  - uid: "101178"
  - uid: "101205"
  - uid: "101376"
  - uid: "101388"
  - uid: "101389"
  - uid: "101546"
  - uid: "101691"
  - uid: "101729"
  - uid: "101758"
  - uid: "101925"
  - uid: "101933"
  - uid: "101941"
  - uid: "101978"
  - uid: "101979"
  - uid: "102000"
  - uid: "102012"
  - uid: "102034"
  - uid: "102046"
  - uid: "102095"
  - uid: "102099"
  - uid: "103217"
  - uid: "103336"
  - uid: "103722"
  - uid: "104477"
  - uid: "106199"
  - uid: "106206"
  - uid: "107523"
  - uid: "107984"
  - uid: "108799"
  - uid: "109084"
  - uid: "109132"
  - uid: "110584"
  - uid: "110959"
  - uid: "111356"
  - uid: "113988"
  - uid: "114057"
  - uid: "114862"
  - uid: "146982"
  - uid: "152696"
  - uid: "152702"
  - uid: "153340"
  - uid: "153414"
  - uid: "153467"
  - uid: "153478"
  - uid: "154619"
  - uid: "154626"
  - uid: "154831"
  - uid: "155956"
  - uid: "156001"
  - uid: "156004"
  - uid: "156298"
  - uid: "163860"
  - uid: "163868"
  - uid: "165335"
  - uid: "165653"
  - uid: "165661"
  - uid: "165668"
  - uid: "165673"
  - uid: "165712"
  - uid: "182066"
  - uid: "182869"
  - uid: "183102"
  - uid: "183404"
  - uid: "222236"
  - uid: "222238"
  - uid: "236954"
  - uid: "238330"
  - uid: "238333"
  - uid: "250474"
  - uid: "250476"
uid-files: "contribution/directx-freeframegl-bridge-files"
title: "[OBSOLETE, see Spout] DirectX-FreeframeGL Bridge"
image: "proof_dx_to_opengl_2.png"
contribution: "true"
---

A plugin that allows for using DirectX Textures in Resolume and probably other OpenGL Freeframe Hosts (which I did not test yet - anyone?). It runs completely on GPU. Multiple textures at the same time are possible.

I use the NVidia Interop Functions. So it only works with NVidia Cards that support these features.

Let me know if you have any issues or hints!

1.  Setup
* VVVV must be started with the /dx9ex command line option in order to support shared resources
* Open the "ShareTextureInfo" help patch
* OR Create a Renderer with something attached to the inlet and use a DX9Texture at the output. In the Inspektor, set the DX9Texture Format to A8R8G8B8 (currently only this Format is supported). Then connect the "ShareTextureInfo" to the Texture output. ShareTextureInfo has an inlet for defining a sharing name for the texture. Change that to whatever you want.
* Copy RR_DXTexture.dll to your plugin directory
* Start Resolume and select DX Texture (RR) from Sources. In the parameters you put the sharing name that you defined in vvvv.

Resolume 4.0 seems to have some issues. Please use more recent Version.

##  For those who want to connect other stuff than VVVV
The Texture Information (Resolution, Share Handle) is transmitted to the plugin via Shared Memory.
The shared memory's name can be set in the plugin's parameters. The Data structure is as follows:

```
struct DX9SharedTextureInfo {
	UINT16 width;
	UINT16 height;
	HANDLE shareHandle;
};
```

*Have Fun! Elio*
##  Links:
* Github Repo of this plugin <https://github.com/meliody/DXTexture2FreeFrame>
* My FFGL Fork (contains the Fix for String parameters) <https://github.com/meliody/FreeFrameGL_15>
* NVidia Interop Specification <https://www.opengl.org/registry/specs/NV/DX_interop.txt>