---
uid: "contribution/art-net-set-for-arduino"
uid-meta: "contribution/art-net-set-for-arduino-meta"
comments: 
 items: 
  - uid: "62663"
  - uid: "62670"
  - uid: "62676"
  - uid: "62678"
  - uid: "62858"
  - uid: "62871"
  - uid: "73989"
  - uid: "96954"
  - uid: "99891"
  - uid: "100612"
uid-files: "contribution/art-net-set-for-arduino-files"
title: "art-net set for arduino"
contribution: "true"
---

Thoses sketchs for the arduino enables you to send it DMX in art-net. You can send 512 channels from VVVV thruth the DMX (art-net Sender) node.

This works with Duemillanove and UNO, on Arduino 22 software.

Contents:

***art-net receiver.pde** wich analyse if packets received are really art-net. see the universe, opcodes. Store in a buffer_dmx values. Up to you to do what you want with it.

***art-net receiver RAW.pde** doesn't analyse anything. Just store the incoming packet as if it was an art-net packet. Dangerous if you use it in non closed and very controlled network.

***art-net et tlc.pde** wich enable you to use a TLC5940NT to increase heavely number of output dimmable you can have on your UNO. 
TLC5940 has 14 output and is daisy chainable. Unfortunately, use of Ethernet Shield and TLC on a same arduino board is physically conflicting. 
For this a hack of the headers in the arduino core header, the ethernet library, and the TLC library. 
Wiring is changed from the usually wiring you may find around.
An html doc ( in french and english ) is included in the folder. 
This hack is  Tofe86 arduino's contribution on the topic of ethernet / TLC conflict.

Just done a little test with my whitecat here: <div class="vimeo embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe title="vimeo-player" data-src="https://player.vimeo.com/video/22679194" width="640" height="360" frameborder="0" allowfullscreen></iframe>
</div>

