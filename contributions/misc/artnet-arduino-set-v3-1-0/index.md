---
uid: "contribution/artnet-arduino-set-v3.1-0"
uid-meta: "contribution/artnet-arduino-set-v3.1-0-meta"
comments: 
 items: 
  - uid: "79168"
  - uid: "79365"
  - uid: "79403"
  - uid: "79447"
  - uid: "81637"
  - uid: "86139"
  - uid: "87710"
  - uid: "91532"
  - uid: "93435"
  - uid: "94268"
  - uid: "97606"
  - uid: "97660"
  - uid: "97671"
  - uid: "97715"
  - uid: "98076"
  - uid: "101859"
  - uid: "104459"
  - uid: "104485"
  - uid: "105441"
  - uid: "173005"
  - uid: "207770"
  - uid: "211892"
  - uid: "254511"
uid-files: "contribution/artnet-arduino-set-v3.1-0-files"
title: "ArtNet arduino set v3.1"
image: "ArduinoWithEthernetShield.jpg"
contribution: "true"
---

Emit to an arduino hardware, or receive data from it over network with vvvv's DMX (artnet) nodes ! 

Those scripts will work with arduino 1.0, and any arduino compatible  with an ethernet or wifi shield. 

Please notice that ethernet shields are using pins to communicate over network data to arduino. Setting digital in setup or trying to write on them will block the script. Have a look to your arduino documentation first about those used pins.

##  V3.1 contains:
**ArtNet receiver v3.1:** performances improvement by MSBerger for arduino software 1.05

**ArtNet receiver SoftPwm:** script for arduino 23, using software pwm to  create false pwm on all io pins

**ArtNet sender:** you can send artnet data from your arduino over network in artnet dmx packet. Sending values of sensors and buttons will be much more easier than all osc or firmata solutions ;-)
Kasper Kamperman has adapted my artnet sender script to work with the arduino software 1.0. Its included in the ArtNet sender 10 folder.

**Folder OLD** contains previous sketches versions


Enjoy !