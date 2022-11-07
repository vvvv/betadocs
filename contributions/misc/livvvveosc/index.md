---
uid: "contribution/livvvveosc"
uid-meta: "contribution/livvvveosc-meta"
comments: 
 items: 
  - uid: "65803"
  - uid: "66242"
  - uid: "66253"
  - uid: "75003"
  - uid: "82481"
  - uid: "86360"
  - uid: "92756"
  - uid: "93121"
  - uid: "93457"
  - uid: "106181"
  - uid: "220335"
  - uid: "220339"
  - uid: "272082"
uid-files: "contribution/livvvveosc-files"
title: "LivvvveOSC"
image: "AbletonClipWindow.png"
contribution: "true"
---

This repository allows extensive remote control of your Ableton Live set either on the same computer or in a network.
It has been tested to work on both PC and Mac; and alongside TouchOSC, the Launchpad, Akai APC, etc.

I tested with a Ableton Live 8 (both Demo and Registered) and with Max4Life . 

Its purpose is to quickly prototype interactive music applications. Almost any control you see in the Clip View of Ableton can be accessed remotely with this collection of tools. Consult the Demo Patch to see some possibilties to read both query the GUI and set various controls.

One of the most valuable properties of this approach is the automatic quantisation when triggering a clip.

##  Installation
1. Copy the "MIDI Remote Scripts\LiveOSC" into your Ableton Live's "Resources" folder.
2. Edit LiveOSC.py in Line 65 to the correct Hosts and Ports (for example to 127.0.0.1, if you want to test it on localhost ports 8008 and 8009)
3. Start Ableton Live
4. In Options->Preferences->MIDI Sync select LiveOSC as a Control Surface
5. Load a set (e.g. "New in Live 8 Demo")
6. Start "Demo Live Ableton.v4p" and start playing around
7. If you want to add LivvvveOSC to your own project, add the repository in the root (Alt+R)


##  Gundel and Dagobert
These helper plugins are useful to get a consistent data set of all current elements of any live set automatically, especially with the Iterate plugin. With these you might be able to build a dynamic GUI in vvvv, similar to TouchOSC' Live Control. 
While Dagobert (German name for Scrooge McDuck) saves and orders everything he gets his hands on, Gundel (German name for Magica de Spell) is more picky to very certain items. All three plugins are meant to circumvene the lack of spreadability of the modules (and of LiveOSC of course).

However, you can identify the IDs of the controls you want to change by trial+error. If you do you will not need either the plugins nor most of the nodes (like Query, Info, Devices, etc)

##  Indexing of Elements
While wrapping the possibilities of LiveOSC into v4 modules i did a few design decisions. 

Every element of Ableton Live has an ID, that can consist of one, two or even three integer values, depending on the type of the element.

1. Scene - Integer counting from 0
1. Track - Integer counting up from 1
1. Mastertrack - Integer 0
1. Return - Integer counting down from -1
1. Clip - TrackID to which the Clip belongs; Integer counting up from 0
1. Device - TrackID, MasterID or ReturnID to which the clip belongs; Integer counting up from 0
1. DeviceParameter - TrackID, MasterID or ReturnID to which the clip belongs; DeviceID; Integer counting up from 0

I found that in Ableton there is a strong divide between tracks and return tracks, even though they have a lot in common (both can be muted, the volume can be controlled, sends can be manipulated, devices like vst effects can be added, etc). I started to treat them transparently where I could (especially in the case of Devices).


##  Limitations
The biggest Limitation is within Ableton and its way to handle the Python script. Since Python (unlike Max) is called by the GUI Thread and not by the Engine thread, it is not real time. You will experience jittery latency between 1 and 16 ms. For time critical purposes it might be wise to add your own Midi constructions. Also the script might affect the performance of Ableton on older computers. 

I wrapped almost everything into modules, the only commands i neglected are the ones to show or highlight stuff in the Ableton Live GUI. Also there might be some Listeners I omitted that are more useful to someone than i anticipated. Consult OSCAPI.txt in the LiveOSC script directory. There are some commands missing in LiveOSC, especially aweful is the lack of polling the number and names of return tracks. 

##  Credits
This contribution is kindly supported by intolight ( http://www.intolight.de ) and the ECAS Network ( http://icasnetwork.org/ ).