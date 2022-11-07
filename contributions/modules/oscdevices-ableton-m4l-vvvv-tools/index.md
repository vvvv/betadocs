---
uid: "contribution/oscdevices-ableton-m4l-vvvv-tools"
uid-meta: "contribution/oscdevices-ableton-m4l-vvvv-tools-meta"
comments: 
 items: 
  - uid: "113898"
  - uid: "114680"
  - uid: "152048"
  - uid: "194267"
  - uid: "228573"
uid-files: "contribution/oscdevices-ableton-m4l-vvvv-tools-files"
title: "OSCDevices: Ableton M4L <-> VVVV Tools"
image: "oscdevices tekcor.jpg"
contribution: "true"
---

This is a set of VVVV module / Max for Live device combinations. Each module/device is meant to run as a pair.

The pack can be used to integrate VVVV generative animation capabilities into sound-production or it can be utilized as a sound-engine for VVVV applications like games or interactive installations.

It runs over network so it is possible to distribute the applications over several computers. An example Ableton Live Set is included.

These four set of modules/devices exist:

- OSC_ClipIn (m4l receive).v4p / OSC_ClipOut.amxd
Receives the data of a clip / sends data of a playing clip in specified track

- OSC_TransportIn (m4l receive).v4p / OSC_TransportOut.amxd
Receives the transport sync from Ableton and produces synced bangs / sends the transport sync from Ableton

- OSC_MidiIn (m4l receive).v4p / LTP_MidiOscOut.amxd 
Send Midi from Live over IP

- OSC_MidiOut (m4l send).v4p / OSC_MidiIn.amxd
Send Midi notes over the network / receives the midi notes

- OSC_Out (m4l send).v4p / OSC_In.amxd
Send up to 8 parameter over the network / receive 8 parameter and map them to any device parameter in the track

PS: If someone need it I also have a clip launching functionality from withing vvvv. Its a bit messy so I didn't add it here so far.