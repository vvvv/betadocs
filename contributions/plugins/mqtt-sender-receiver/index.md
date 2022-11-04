---
uid: "contribution/mqtt-sender-receiver"
uid-meta: "contribution/mqtt-sender-receiver-meta"
comments: 
 items: 
  - uid: "193430"
uid-files: "contribution/mqtt-sender-receiver-files"
title: "MQTT Sender & Receiver"
contribution: "true"
---

**MQTT** 
short for Message Queue Telemetry Transport, is a light weight open Source messaging protocol for the Internet of Things. 
Learn more:
* http://mqtt.org/
* http://www.redbooks.ibm.com/abstracts/sg248054.html

**Why should I use it?**
MQTT is a great and **easy** way to exchange low frequency messages like sensor readings, or program states etc. between multiple machines and services. Its very robust with a small footprint. 
It is based on the publish/subscribe paradigm and requires a central MQTT Broker.

**Cool:** 
* You can host the broker in the public web and communicate with nodes in local networks.
* Which means you can communicate with your an Arduino anywhere on the planet which is connected to the internet: <https://github.com/knolleary/pubsubclient> 
* The communication is asynchronous and won't block vvvv!

If you wan't to host your own broker have a look at: 
* Simple but powerful broker: <http://mosquitto.org/>
* Full IoT stack including an MQTT broker for the Rasperry PI: <http://thethingbox.io/> 

**Funfact:** 
The Facebook Messenger is build on MQTT: <https://www.facebook.com/notes/facebook-engineering/building-facebook-messenger/10150259350998920>

Find the code at GitHub: <https://github.com/JOxBERGER/VVVV-MQTT>

This is a beta release, it works *most* of the time ;)