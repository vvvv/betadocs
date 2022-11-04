---
uid: "contribution/mre-mdmod"
uid-meta: "contribution/mre-mdmod-meta"
comments: 
 items: 
  - uid: "90116"
  - uid: "90124"
  - uid: "90155"
  - uid: "90158"
  - uid: "90161"
  - uid: "90172"
  - uid: "90184"
  - uid: "90186"
  - uid: "90188"
  - uid: "90197"
  - uid: "90199"
  - uid: "90210"
  - uid: "90211"
  - uid: "90261"
  - uid: "90668"
  - uid: "93561"
  - uid: "93565"
  - uid: "93572"
  - uid: "93578"
  - uid: "101274"
  - uid: "101287"
  - uid: "174157"
  - uid: "174366"
  - uid: "174867"
uid-files: "contribution/mre-mdmod-files"
title: "[OBSOLETE] MRE mdmod"
image: "mre.mdmod_.test-DirectX Renderer4.png"
contribution: "true"
---

##  OBSOLETE! Go for DX11 ;)
WARNING: THIS IS A HUGE RESOURCEHOG! the maximum resolution i squeezed out of it was 1280*720 @ 34 fps without mainloop limiting. and as i know i don't have a crappy hardware.

Update2: i know dx11 is coming next year so this stuff will become obsolate in a short time i guess but until then:
* added deferred shadows and lighting which saves 0 performance currently (even deferred lighting is slower) so i do something completely wrong but you have another pass you can play with
* added a LensBlur filter based DOF which is slower but sometimes nicer
* added some transparency support (alpha inside scene)
* added a dynamic vectorfield based particle system.
* smoothed light range out with a power option
* fixed delayed shadows
* fixed a bunch of other stuffs i don't remember now
* revamped examples (mre.mdmod.test.*.v4p)
* i still cannot find a reason why ATI cards doesn't like this
* on particles for the future: Vadim Smakhtin (it's a shame but i don't know his nickname here) started to implement his modular particle system inside mre.mdmod on github here: https://github.com/smakhtin/MRE.mdmod and that will be super-awesome!

Update1: based on some feedback there are some situations where the whole screen would go black after some time or start to flicker to black for one frame randomly and this may present on lower end or older graphics cards. I have no idea what could cause this apart from low performance. I've did some fix to ToneMapping which should get rid of the problem but it's not 100%.
Also i've noticed a stupid bug in Phong Static it's fixed now.

see mre.mdmod.test.v4p to see how to use it!
this is a complete revamp of MRE you don't need the original to use this however they can work besides eachother

##  what's new in mre.mdmod:
* 4th rendertarget used for velocity
* replaced the DOF with a slower but nicer one
* added a BlurPerfector to SSAO now it's nicer
* replaced pipet in ToneMapping with a GPU only method. now that's faster
* added motion blur
* Phong shader got some overhaul:
* multiple point lights
* different soft-shadows engine (nicer but slower than VSM)
* displacement, normal and bump mapping (via cone-mapping)
* different emission and ambient color
* specular mapping
* reflection / refraction

## lights:
* currently only point lights are supported
* number of lights will be determined by the number of light position vectors
* light data texture format is:
row1: RGB: position; A: range
row2: RGB: color; A: strength
* select the main light which will cast shadows by Main Light Index
* it has optional deferred lighting (lighting in post-process)

## shadows:
* Shadow Samples determines how many samples will be used for softening. 9 is a good number it's not too ugly but it's not too slow
* Shadow Softness determines how spreaded the softening samples should be (0 means hard shadows in this case you can set sample count to 1)
* Shadow Distance multiplier determines the speed of increment of the softness on the distance between the shaded point and the light source
* Noise is just noise. since i don't know how to interpolate between the softening samples ugly artifacts can be replaced with less ugly artifacts. consumes performance however
* Shadow Contrast is the area of interpolation starting after the shadow bias between bright and fully shaded. low numbers can reveal artifacts
* it has optional deferred shadows (calculating shadows in post-process instead of in the scene)

## DOF:
* "autofocus" could be set by "AF Point" on screen space ranging from -1 to +1, "lerpAF" which interpolates between manually set focus distance, filterAF is the time filter for autofocus and the actual focus distance is calculated from the average of distances inside the rectangle defined by "AF Area" (in the examples focus with your mouse)
* "manual focus" is set by distance both background and foreground blurring can be set separately

## Todo:
* spot and directional light support.
* alpha support for the output texture.