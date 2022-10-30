---
uid: "contribution/peak-can-usb"
uid-meta: "contribution/peak-can-usb-meta"
comments: 
 items: 
  - uid: "98883"
  - uid: "105105"
uid-files: "contribution/peak-can-usb-files"
title: "Peak CAN USB"
contribution: "true"
---

Use with the Peak USB adapter ( http://www.peak-system.com ).
This can i.a. be used to communicate to most Cars on-board electronics.

NB: There is a bug when connect is enabled on startup which causes vvvv to freeze. So use a OnOpen with some delay.

The Init Buffer Pin Copies the current input to a temporary buffer. Use the the Send Pin to send the buffer messages. (The buffer is used for sending cyclic messages which need accurate timing)
For other messages just use the "Send Message every Milli.." Pin. Where 1 = Sending.

I have some other variations of this plugin with e.g. direct use of RAW data etc. If you need any other give me a hint.