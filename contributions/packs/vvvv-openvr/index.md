---
uid: "contribution/vvvv.openvr"
uid-meta: "contribution/vvvv.openvr-meta"
comments: 
 items: 
  - uid: "223880"
  - uid: "223881"
  - uid: "223883"
  - uid: "223884"
  - uid: "223919"
  - uid: "223924"
  - uid: "223926"
  - uid: "223935"
  - uid: "224709"
  - uid: "224755"
  - uid: "224757"
  - uid: "225045"
  - uid: "225046"
  - uid: "225316"
  - uid: "225321"
  - uid: "226064"
  - uid: "226541"
  - uid: "226542"
  - uid: "227946"
  - uid: "228000"
  - uid: "228160"
  - uid: "228241"
  - uid: "228379"
  - uid: "228386"
  - uid: "228607"
  - uid: "228608"
  - uid: "228621"
  - uid: "228627"
  - uid: "228820"
  - uid: "228825"
  - uid: "228884"
  - uid: "228888"
  - uid: "228895"
  - uid: "228964"
  - uid: "229310"
  - uid: "229531"
  - uid: "229535"
  - uid: "229638"
  - uid: "229644"
  - uid: "229660"
  - uid: "229663"
  - uid: "230823"
  - uid: "230827"
  - uid: "230829"
  - uid: "230842"
  - uid: "232202"
  - uid: "232208"
  - uid: "232209"
  - uid: "232210"
  - uid: "232252"
  - uid: "232253"
  - uid: "232404"
  - uid: "232843"
  - uid: "232964"
  - uid: "232992"
  - uid: "232999"
  - uid: "233631"
  - uid: "233632"
  - uid: "234551"
  - uid: "234553"
  - uid: "235090"
  - uid: "235141"
  - uid: "235149"
  - uid: "235156"
  - uid: "235157"
  - uid: "235158"
  - uid: "235159"
  - uid: "235161"
  - uid: "235165"
  - uid: "235167"
  - uid: "235261"
  - uid: "235336"
  - uid: "239015"
  - uid: "239038"
  - uid: "239039"
  - uid: "239040"
  - uid: "240922"
  - uid: "240934"
  - uid: "240936"
  - uid: "242055"
  - uid: "242813"
  - uid: "242816"
  - uid: "243406"
  - uid: "245861"
  - uid: "246183"
  - uid: "247133"
  - uid: "248442"
  - uid: "248469"
  - uid: "249390"
  - uid: "249391"
  - uid: "250914"
  - uid: "250939"
  - uid: "250940"
  - uid: "250979"
  - uid: "250980"
  - uid: "250983"
  - uid: "250985"
  - uid: "251724"
  - uid: "251729"
  - uid: "251731"
  - uid: "251732"
  - uid: "254298"
  - uid: "254370"
  - uid: "254372"
  - uid: "254378"
  - uid: "254414"
  - uid: "254512"
  - uid: "255382"
  - uid: "273102"
  - uid: "273217"
  - uid: "278050"
  - uid: "278060"
  - uid: "278416"
  - uid: "279478"
uid-files: "contribution/vvvv.openvr-files"
title: "VVVV.OpenVR"
image: "product-family-steamlogo [33%]_0.png"
contribution: "true"
---

1. VVVV.OpenVR
The OpenVR pack contains nodes to get pose data and render a 3D scene into any VR headset supported by SteamVR. Currently HTC Vive, Vive Pro, Oculus Rift DK1, DK2 and CV1. Basically, all headsets supported by SteamVR.

**Commissioned** by Marshmallow Laser Feast:
http://marshmallowlaserfeast.com/

**Special thanks** goes to these members of the vvvv community who also supported its development with various amounts:

<!--{SPLIT()}-->
Chris Engler
[/businesses/wirmachenbunt](https://vvvv.org/businesses/wirmachenbunt)
Hamburg, Germany

Paul Scheytt
[/businesses/decode](https://vvvv.org/businesses/decode)
Hamburg, Germany

[ggml](http://vvvv.org/users/ggml)
http://cote.ggml.ro/
Bucharest, Romania

Andres Alvarez
[andresc4](http://vvvv.org/users/andresc4)
Rosario, Argentina

Thomas Bouaziz 
[/businesses/experienss](/businesses/experienss)
Paris, France

<!--~~~-->
Louis Mustill & Will Young
[mrboni](http://vvvv.org/users/mrboni)
London, UK

[colorsound](http://vvvv.org/users/colorsound)
[/businesses/colorsound-ixd](/businesses/colorsound-ixd)
Granada, Spain

schnellebuntebilder
[/businesses/schnellebuntebilder](https://vvvv.org/businesses/schnellebuntebilder)
Berlin, Germany

Eno Henze
[/businesses/nsynk](https://vvvv.org/businesses/nsynk-gesellschaft-f%C3%BCr-kunst-und-technik)
Frankfurt/Main, Germany

Christoph Schmid [knaif](http://vvvv.org/users/knaif)
www.lichterloh.tv 
Vienna, Austria

<!--{SPLIT}-->

### Code Contributions
* additions to controller nodes by [herbst](http://vvvv.org/users/herbst)
* trigger haptic pulse by [sebl](http://vvvv.org/users/sebl)
* disable wait for sync [microdee](http://vvvv.org/users/microdee)

### Nodes
**Poser (OpenVR)** returns all tracking poses from the headset, lighthouse stations, trackers and controllers as transformation. Also has a pin to disable wait for OpenVR sync, but the sync needs to run a few times in startup to get the compositor up and running.

**Camera (OpenVR)** calculates vvvv conform view and projection matrices for the left/right eye. It also outputs the recommended texture size and a hidden area mesh that masks out unnecessary pixels to safe shader performance.

**Compositor (OpenVR)** receives a texture handle and submits it to the HMD.

**TrackedDevices (OpenVR)** outputs all OpenVR events and an object oriented view on the tracked devices. Might be merged with Poser in the future.

**Controller (OpenVR Split)** splits a tracked controller from the TrackedDevices node into pose transformation, trackpad axis and all button states.

### Modules
**Renderer (OpenVR DX11)** Combines Camera and Compositor into one handy node that only needs a layer to be rendered. It exposes quality settings and returns the rendered texture for preview.

**HiddenArea (OpenVR DX11.Layer Viewport)** constructs the hidden area mesh to cast out unnecessary pixels.

**ViveController (OpenVR DX11.Layer)** renders a life-like model of the vive controller. It gives a pretty good eye-hand coordination feeling when seeing the actual controller in VR.

**ViveLighthouse (OpenVR DX11.Layer)** renders a life-like model of the vive lighthouse tracking station.

**HMD (OpenVR DX11.Layer)** renders a life-like model of a generic VR headset, helps to build a third person overview on the scene.

### Vive Trackers
Latest version has **tracker only support**, read this blog post on how to set it up: [using-htc-vive-trackers-without-headset](/blog/using-htc-vive-trackers-without-headset)

### Learning
Here is a nice set of patches from the OpenVR beginner workshop from NODE17:
[node17-openvr-beginner-material](xref:contribution/node17-openvr-beginner-material)

### Setup
- Make sure the [DX11 pack](xref:contribution/directx11-nodes) is installed
- Place the VVVV.OpenVR folder into vvvv's packs folder
- Use SteamVR to calibrate your room
- Start the patch 01_OpenVRDemo.v4p in the \girlpower folder to test the setup

### Github
Sources are available here:
https://github.com/tebjan/VVVV.OpenVR

If you encounter bugs, then github issues instead of comments are welcome:
https://github.com/tebjan/VVVV.OpenVR/issues