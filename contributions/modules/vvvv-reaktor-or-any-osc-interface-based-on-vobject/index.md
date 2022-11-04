---
uid: "contribution/vvvv-reaktor-(or-any-osc)-interface-based-on-vobject"
uid-meta: "contribution/vvvv-reaktor-(or-any-osc)-interface-based-on-vobject-meta"
comments: 
 items: 
  - uid: "201862"
  - uid: "201865"
  - uid: "202007"
  - uid: "220271"
  - uid: "247042"
  - uid: "247043"
  - uid: "247045"
  - uid: "247046"
  - uid: "247047"
  - uid: "247048"
  - uid: "247049"
uid-files: "contribution/vvvv-reaktor-(or-any-osc)-interface-based-on-vobject-files"
title: "VVVV <---> Reaktor (or any OSC) interface based on VObject"
image: "preview_4.png"
contribution: "true"
---

Modular, cable free system to send OSC messeages
DEATH TO CONS!

Installation:
you **need** to have this:
https://github.com/microdee/VVVV.Packs.VObject
in your packs folder in VVVV

**Why should I want this?**
First of all, reaktor is a great tool for sound, and when you want to build interface in vvvv that talks through UDP, it usually means a LOT of cables and cons nodes, this little module make them disappear, leaving you with modular system that does not needs cables, can access one OSC value from multiple places in VVVV just by using OSC name, and can be expanded with more functionality easily.

**What is a Vobject?**
Vobject is a system from microdee, that you always wanted in VVVV, but never knew about it. It could be system for distributing multiple S nodes to one R node, or it could be system for managing skeletons and other information from Kinect. These are just two examples and this module is built on the first one. This is a great place for learning Vobject, which has a huge pontential in data handling! (also featured on Emeshe, which was not yet featured in TV commercials unfortunately)

**What is missing?**
I took out few features out of first realease, specifically I found a way how to receive drum triggers from reaktor sequencer faster, when setting UDP to Spread queue mode. Its a bit tricky, I need to play a bit more with it so I know it really works. Right now the Discard mode is most accurate for knobs, faders, etc.

There are many possibilities what and how to control in Reaktor, particularly useful is snapshot switching, you can find that in original files from Reaktor workshop (link in credits). 

I could have made the decision to distribute RAW data in VObject directly without changing it to string, but i did not (had some problems with crashing). This is probably more stable.

I have not tested this in huge application, but I am building a live performance on this system so updates are expected.