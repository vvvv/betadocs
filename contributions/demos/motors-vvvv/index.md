---
uid: "contribution/motors- -vvvv"
uid-meta: "contribution/motors- -vvvv-meta"
comments: 
 items: 
  - uid: "273290"
uid-files: "contribution/motors- -vvvv-files"
title: "Motors + VVVV"
image: "ws_leipzig2011.jpg"
contribution: "true"
---

Since it was quite a hands-on workshop with mostly hardware - there is not so much material to share. In the zip you will find a PDF with all the collected circuits and one stepper example (VVVV + arduino patch). 

1) For Servos just use the fantastic Firmata nodes (coming with the addonpack) by jens.a.e & u7angel (upload firmata to arduino first)

> connect servo as shown in pdf and select "servo" in enumeraion IO Box for the used pin. The rest is explained quite well in the Firmata helppatch.

2) For DC-motors, also use the Firmata nodes

> connect a double h-bridge like the ln293d as shown in the pdf with an Arduino, external voltage and a motor. 

In the firmata helppatch you need three pins for your motor. One digital out with a PWM ouput. Another two digital outputs just with HIGH/LOW output. 
The PWM defines the speed of your motor
the other two work as followed:
pin1: HIGH, pin2: LOW -> left rotation (depending on your setup)
pin1: LOW, pin2: HIGH-> right/inverse rotation
both HIGH should stop the motor (creates a kind of shortcut) do not do this too long...

(most of the standart motorshields you get for the arduino should work the same way)

3) For Steppermotors use the stepper example and a stepperdriver like a ln293d or for better control something like the pololu 4988 or the easydriver from sparkfun, you need to upload the arduino patch "stepper_RS232_Control_ino"

One very fancy but expencive alternative for steppers are the stepperdrivers from phidget which have a plugin in vvvv.


you might want to know what PWM is:
http://en.wikipedia.org/wiki/Pulse-width_modulation