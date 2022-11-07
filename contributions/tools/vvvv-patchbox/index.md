---
uid: "contribution/vvvv-patchbox"
uid-meta: "contribution/vvvv-patchbox-meta"
comments: 
 items: 
  - uid: "205784"
  - uid: "205801"
  - uid: "205805"
  - uid: "205807"
  - uid: "205927"
  - uid: "205940"
  - uid: "206423"
  - uid: "206461"
  - uid: "206492"
  - uid: "207512"
  - uid: "208750"
  - uid: "208768"
  - uid: "208771"
  - uid: "208830"
  - uid: "209143"
  - uid: "210465"
  - uid: "229327"
  - uid: "229398"
  - uid: "248176"
  - uid: "248177"
  - uid: "248178"
  - uid: "248219"
  - uid: "248334"
  - uid: "249335"
  - uid: "249350"
uid-files: "contribution/vvvv-patchbox-files"
title: "vvvv-Patchbox"
image: "pedalboard.jpg"
contribution: "true"
---

This toolset gives you some additional capabilities to patch with great speed. 

Yes, thats right: it improves your thought-to-patch-ratio by over 9000!


##  Install
Download, place somewhere on disk (e.g. the girlpower folder of your vvvv). Drag'n'Drop into your root.v4p (can be opened with Alt+R while running vvvv) and save.

##  Usage
There are seven things available right now:

###  Node Creation
####  Patchlet
Retrieve the contents from a patch (e.g. mainloop.v4p) and paste it at the mouse position by typing:

make mainloop 

Other prefab patchlets are in the /Patchlet folder, like tty or render9
Add your own.



####  Operandomatic
Doubleclick somewhere and type something like

@1 (to create a GetSlice with a preset index of 1)
+-1 (to create a + with a preset second operand of -1)
i5 (to create an I with a running length of 5)
etc. 

###  IOBox
####  IOScaler
Hold down the right mouse button while resizing an IOBox to fit the font size accordingly.

While scaling or moving an IOBox you can use the mouse wheel to add rows and columns to the iobox.

####  IOType
While scaling or moving an <span class="node">IOBox (Value Advanced)</span> you can hit i, b or f to change the Value Type (Integer, Boolean or Real aka Float)

####  MagicIO
Doubleclick somewhere and type something like 

io4x4 (to create a four-by-four iobox matrix of values)
string5 (to create a iobox list of 5 strings)
enum1x3 (to create a horizontal list of 3 enums)
press3x2 (to create a two-by-three iobox matrix of booleans, preconfigured to be pressed)
etc.

###  Patch
####  Commander
Hold Alt+Space to hide your current patch window. Releasing the shortcut will force the window to redraw, so you can simply make any gui glitch disappear.

Use Alt+Left/Right to move your current patch window in a similar manner as you are used from other windows with the Win+Left/Right shortcuts. The code to do so is modularized, you can make your own layout just as easily.

####  SnapToGrid
Hold down Space while moving/resizing nodes or ioboxes to make them snap to an invisible grid.

##  Remarks
While the original patches of many contributors were quite diverse in their approach (plugins, regex, in-string-replacements and whatnot) I took the liberty of homogenizing them towards XElement/XPath usage and modularizing them, so they can be combined and extended more easily. I hope some of the mechanics can make VL a better GUI.

More helpers can be integrated (like project statistics, an exporter, a in-patch git prompt or whatever you come up with) to increase project productivity. Choose active Improvements as you wish, there is no harm in disabling some.

Feel free to [clone](https://github.com/velcrome/vvvv-Patchbox) and pullrequest your feature into the code. 