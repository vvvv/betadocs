---
uid: "contribution/arduino-network-firmata-updated"
uid-meta: "contribution/arduino-network-firmata-updated-meta"
comments: 
 items: 
  - uid: "213193"
  - uid: "213488"
  - uid: "216225"
  - uid: "242052"
  - uid: "242054"
uid-files: "contribution/arduino-network-firmata-updated-files"
title: "Arduino Network Firmata - UPDATED"
image: "Arduino (NetworkFirmata).jpg"
contribution: "true"
---

It works with WIZ5100-based ethernet-shield, Arduino Ethernet, ENC28J60 or Yun, but right now, the arduino code is set up for the ENC28J60  as i used it.
If u need it for a different board, just modify the arduino code for your needs in "CustomFirmata" accordingly.
Then set it up with your custom ip, mac or whatever.
I have personally tested it with ENC28J60 and it works like the regular firmata.
It might also not connect right away, but it will connect, so, patience.
Oh, btw the arduino connects to the PC running running the vvvv plugin, so leave the plugin enabled.
Keep in mind to have the same port in both devices(pc, arduino), and the corresponding ips inserted. 
Hope it work for you as it works for me.
PS: this is my first post, so don't really know if everything is forum-law-wise :D.
