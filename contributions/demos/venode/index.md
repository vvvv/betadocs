---
uid: "contribution/venode"
uid-meta: "contribution/venode-meta"
comments: 
 items: 
  - uid: "93263"
  - uid: "93265"
  - uid: "93266"
  - uid: "93275"
  - uid: "93280"
  - uid: "93291"
  - uid: "93300"
  - uid: "93301"
  - uid: "93316"
  - uid: "93317"
  - uid: "93330"
  - uid: "93967"
  - uid: "93969"
  - uid: "93971"
  - uid: "93986"
  - uid: "93988"
  - uid: "93991"
  - uid: "94030"
  - uid: "95463"
  - uid: "96872"
  - uid: "96907"
  - uid: "100052"
  - uid: "102644"
  - uid: "103332"
  - uid: "104061"
  - uid: "104128"
  - uid: "107527"
  - uid: "107531"
  - uid: "173059"
  - uid: "173067"
  - uid: "183728"
  - uid: "184029"
  - uid: "184110"
  - uid: "190637"
  - uid: "196807"
  - uid: "218431"
  - uid: "218439"
  - uid: "218445"
  - uid: "218500"
  - uid: "218511"
  - uid: "218517"
  - uid: "218527"
  - uid: "218630"
  - uid: "218634"
  - uid: "218651"
  - uid: "218887"
uid-files: "contribution/venode-files"
title: "Venode"
image: "nodejs-1024x768.png"
contribution: "true"
---

Here is a demo showing interaction between nodejs and vvvv.
*Node.js is a platform built on Chrome's JavaScript runtime for easily building fast, scalable network applications. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfect for data-intensive real-time applications that run across distributed devices.*


This demo show how you can interact with an html browser to get data and set data in realtime with multiple user/device using javascript.
Node act as a single lightweight server and communicate with vvvv with the  udp protocol.


**In order to have this demo working you first need to install node.js**
download here http://nodejs.org/]  once installed start the nodejs.v4p clic on start nodejs then open your browser <http://localhost:8000/>
 

Feedback are welcome  for bug device suported...
tested on firefox win7 /chrome win7  /safari osx/safari ios6/
This is a demo and it is here as a starter for further devellopement, the message protocol should be replace with json in the future for better communication and cleaner code.

If you use this work for your project be nice and credit me.

**Latest update to version 0.5**

I have rewritten venode nearly from scratch and made several improvements:

* new: communication completely via JSON
* new: consistent session & data storing in vvvv
* new: added message interval to avoid too many pushes (important for mobile devices)
* new: responsive weblayout (with skeleton)
* new: added more UI elements (colorpicker, 2dpad, bang & toggle button)
* bugfix: call removeListener() only for disconnected client instead of removing all listeners

Next steps could be to implement OSC messages to have a more efficient client-server communication. Also new UI elements can be added: carousels, datepickers, modals, progressbars,..

Feedback welcome!
If you use this for your projects be nice and credit [www.intolight.de