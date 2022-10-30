---
uid: "contribution/vvvvimba-gige-camera-plugin"
uid-meta: "contribution/vvvvimba-gige-camera-plugin-meta"
uid-files: "contribution/vvvvimba-gige-camera-plugin-files"
title: "VVVVimba - gigE Camera Plugin"
image: "url.jpg"
contribution: "true"
---

Plugin to stream Video from Vimba gigE Cameras.  <http://www.alliedvisiontec.com>
Only tested with a single Mako223 cam (greyscale).
Definitely needs some tweaking and cleaning but it worked well for us.

1.  Installation
create a \packs folder next to \girlpower (in case you don't have it yet)
unzip elliot's imagepack, the \Image folder lands in the \packs folder (i.e. just next to \DX11 if you also have the dx11 pack) - make sure you have the nvcuda.dll !
Copy the VimbaSDK.dll into \image\nodes\plugins
Install the VimbaSDK <http://www.alliedvisiontec.com/us/products/software/vimba-sdk.html>

OR

just build everything from scratch (recommended) by following the instructions in the readme on github

<https://github.com/struktstudio/VVVVimbaSDK>

1.  Features
- Stream video directly into vvvv as CV Image

- theoretically set every single feature available by the cam in use with the fully spreadable SetFeature (Vimba) Node - too many to test them all, so some settings might break something...

-  probably supports multiple cameras, but we only had one to test it...

- helppatch in the /bin folder

1.  Known Issues
- some unusual width and height settings seem to not work so well with AsTexture (CV.Image)

- it's only 8 bit greyscale for now (as that's what our camera at hand supported)

###  Credits and License
elliotwoods and his imagepack, robi_h, soriak
Developed at  <http://www.strukt.com>
Creative Commons - ShareAlike
