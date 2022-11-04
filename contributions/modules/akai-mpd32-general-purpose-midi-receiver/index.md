---
uid: "contribution/akai-mpd32-general-purpose-midi-receiver"
uid-meta: "contribution/akai-mpd32-general-purpose-midi-receiver-meta"
comments: 
 items: 
  - uid: "110762"
  - uid: "152148"
uid-files: "contribution/akai-mpd32-general-purpose-midi-receiver-files"
title: "Akai MPD32 general purpose MIDI receiver"
image: "MPD32-MIDI-general_V3_screenshot.png"
contribution: "true"
---

This patch collects all MIDI Input from an Akai MPD32 and serves them in a convenient way.
I use to scroll down and use frameless Mode (<[Ctrl>-<8>) to have a view on 
current values (fitting 1080 screen lines)
* The drum pads trigger regular Bangs as well as a sustaining signal ("hold" until Note Off)
   and an ordinal of the last pressed Pad, together with four Bangs telling which Pad Bank is active.
* The beat uses MPDs Clock. Hit the <[PLAY> transport button on the device and <[TAP%20TEMPO>.
* Choose one of 7 slices of the Beat Bangs to synchronize parameters of your Set from 1/16th up to 4/1. 
* All values are exported per Output Pin as well as per <span class="node">S (Value)</span>.

Currently i haven't installed the Vyzex Software to attach the MPD preset in the proprietary format. If you experience problems uploading the SysEx, let me know.

Have fun, any feedback welcome.