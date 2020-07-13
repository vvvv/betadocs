---
uid: 5b3459c4-ea4a-40a1-8bf9-60d4c0a0f5ef
---

# Firmata

Firmata is a protocol for communicating with microcontrollers from software on a computer (or smartphone/tablet, etc).  

The <span class="node">FirmataBoard (Devices)</span> node is able to talk to any microcontroller board (like Arduino, Teensy, Particle.io, ...) that is loaded with the Firmata firmware or uses the Firmata library.  

For example, this is how to setup an Arduino Board:  
* Open the <a href="https://www.arduino.cc/en/Main/Software" class="extURL" target="_blank">Arduino IDE</a>, choose File > Examples > Firmata > StandardFirmata.   
* Choose your 'Board' and the 'Port' under the 'Tools'.   
* Click Upload. Your Arduino is ready.  


![](~/img/vvvv-ArduinoSecondService_10fps.gif "")   
The *FirmataBoard (Devices) node in action.*  

# An Overview
![](~/img/vvvv-FirmataSecondService_wide2.png "")   
*Basic setup.*  

The extensive helppatch of <span class="node">FirmataBoard (Devices)</span> explains all the details regarding reading and writing data, as well as some advanced topics like using the I2C protocol or a custom Firmata firmware. Here is just a short overview:  


* Use <span class="node">DigitalWrite (Firmata)</span>, <span class="node">AnalogWrite (Firmata)</span> or <span class="node">ServoWrite (Firmata)</span> nodes to set the pins of the board.  
* Use <span class="node">DigitalRead (Firmata)</span> and <span class="node">AnalogRead (Firmata)</span> nodes to get values from the board's pins.  
* Use the <span class="pin">Sysex Messages</span> output to receive different 'Sysex Messages' sent back by the microcontroller board. Some Sysex decoders are already there (<span class="node">StringDecoder (Firmata)</span>, <span class="node">CapabilityResponse (Firmata)</span>, ...)  

* The <span class="node">FirmataBoard (Devices)</span> is able to talk to any microcontroller board loaded with the standard <a href="https://github.com/firmata/protocol/blob/master/feature-registry.md#core-feature-set" class="extURL" target="_blank">Firmata</a> firmware without any further configuration. In the Arduino-world such Firmata firmware is called "StandardFirmata".  
* Have some custom Firmata running on your chip? Just provide the configuration manually using the <span class="node">BoardConfig (Firmata)</span>.  


The nodes were developed together with <span class="user"><a href="https://vvvv.org/users/jens.a.e" class="extURL" target="_blank">jens.a.e</a></span>, author of the original (now legacy) <span class="node">Arduino (Devices StandardFirmata 2.x)</span> node.   


**Examples in your vvvv\ directory:**  
* girlpower\IO\Arduino  
* girlpower\VL\Firmata  

**See also:**  
* <a href="https://github.com/firmata/protocol#firmata-protocol-documentation" class="extURL" target="_blank">Firmata Protocol Documentation</a>  
* <a href="https://vvvv.org/contributions/1353+1351+2439+1352+7934+2438+1354+1355/4127+3036+5126+2446+4118+3791" class="extURL" target="_blank">Related Contributions</a>  
* <a href="http://prototypinginterfaces.com/category/patches/" class="extURL" target="_blank">Patches from the 'Prototyping Interfaces' book</a>