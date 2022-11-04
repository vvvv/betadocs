---
uid: "contribution/textflock-(spreads)"
uid-meta: "contribution/textflock-(spreads)-meta"
comments: 
 items: 
  - uid: "101571"
uid-files: "contribution/textflock-(spreads)-files"
title: "TextFlock (Spreads)"
contribution: "true"
---

You provide a spread of strings. 
This module will scramble the words into particles and then morph to the next text at time selectable by you. 
Take manual control to go to pause or go to specific strings.
Get output as a layer or x/y positions to plug into your own particles.

See the help patch for more info. 

All done on the CPU, no shaders.

Text can look funny due to how TypoSpread handles it. (For instance add extra spaces between words or gaps will be too small) 
If you were so inclined you could easily build a memory structure that allowed you to recall position and spacing for every letter individually.

Originally developed for Wired #NextFest 2013 Milan, Italy. 

V1.1 - Fixed bug in helppatch where 'Active Now' spread was connected by slice index instead of Y input