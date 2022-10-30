---
uid: "contribution/aiir-(animation).v4p"
uid-meta: "contribution/aiir-(animation).v4p-meta"
comments: 
 items: 
  - uid: "160423"
uid-files: "contribution/aiir-(animation).v4p-files"
title: "AIIR (Animation).v4p"
image: "AIIR (Animation) help.png"
contribution: "true"
---


####  AIIR (Animation).v4p - an Adaptive Infinite Impulse Response Filter
simplified and short:
.
a IIR Filter with dynamic delay ratio.

the delay ratio depends on the Input's Frame Velocity.

means:
small framedifference --> strong filtering
large framediffence --> almost no filtering.

this way 
noise is filtered smoothly
but peaks can pass almost unfiltered.


credits to tonfilm for the original inspiration!
back then in 2007 i *\*\*HAD\*\** to put this into  a module. 

<div class="box">
see http://legacy.vvvv.org/tiki-index.php?page=kalle.Modules.Animation
see http://en.wikipedia.org/wiki/Infinite_impulse_response</div>