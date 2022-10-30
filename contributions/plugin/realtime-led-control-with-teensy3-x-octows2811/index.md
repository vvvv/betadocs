---
uid: "contribution/realtime-led-control-with-teensy3.xoctows2811"
uid-meta: "contribution/realtime-led-control-with-teensy3.xoctows2811-meta"
comments: 
 items: 
  - uid: "102352"
  - uid: "105237"
  - uid: "105298"
  - uid: "105318"
  - uid: "105449"
  - uid: "113906"
  - uid: "114219"
  - uid: "114231"
  - uid: "114241"
  - uid: "114277"
  - uid: "114302"
  - uid: "114517"
  - uid: "114538"
  - uid: "114563"
  - uid: "204502"
  - uid: "205086"
  - uid: "218528"
  - uid: "218579"
  - uid: "218886"
  - uid: "218912"
  - uid: "221369"
  - uid: "221392"
  - uid: "238823"
  - uid: "238825"
  - uid: "238826"
  - uid: "239238"
  - uid: "246446"
  - uid: "246447"
  - uid: "247160"
  - uid: "247689"
  - uid: "249492"
uid-files: "contribution/realtime-led-control-with-teensy3.xoctows2811-files"
title: "Realtime LED control with Teensy3.x/OctoWs2811"
contribution: "true"
---

Build your own low cost global DIY video walls, or just control a number of mapped, ultra-bright LED strips along an arbitrary structure!

The [OctoWS2811](http://www.pjrc.com/teensy/td_libs_OctoWS2811.html) library is for the [Teensy3.x](https://www.pjrc.com/teensy/teensy31.html) board and can drive 1k of 24bit color LED's at high video frame rates easily. 

This contribution allows you to feed your own simple 300W LED real time installation. You'll need the following ingredients (links show the parts we worked with, there might be other, better and worse):

1 running German [vvvv](https://store.vvvv.org/)
4 China Rolls of [4m LED](http://www.shiji-led.com/en/productshow.asp?id=765&sid=175) (each ~€50, check your local suppliers and alibaba, try asking for custom build like waterproof IP67, special lengths or prefab connectors)
1 USA Teensy (€20) with a MicroUSB Cable (>€3)
1 [Octows2811 Adapter](https://www.pjrc.com/store/octo28_adaptor.html) (€6)
2 halves of a CAT6 cable (€0 if you salvage the healthy ends of a broken cable)
1 5 VCD [power supply](https://www.google.de/webhp?q=meanwell+sp-320-5&tbm=shop), slightly overpowered (100€)

Just [add](https://www.youtube.com/watch?v=e-rdgB_19Fg) solder, connectors, some surface and some strong cables.

Scale as you may, at least eight teensies with 1k RGB-LED each can been controlled even with basic serial interfacing over a solid USB3 hub and the help patch (that'd be >=48 dmx universes). Development towards ethernet control is under way, which promises even better better scalability. Support is welcome!

This European contribution is rollware: if you buy or sell WS2811 rolls (aka WS2812b) while utilizing this code or parts of it, please snailmail additional roll(s) for the authors: one meter for every eight is cool. If you roll your own code with it, leave credit to the authors. Original patch was by [catweasel](http://vvvv.org/users/catweasel), c# plugins are from [velcrome](http://vvvv.org/users/velcrome)