---
uid: "contribution/windowhandler-(vvvv)"
uid-meta: "contribution/windowhandler-(vvvv)-meta"
comments: 
 items: 
  - uid: "246758"
  - uid: "246760"
  - uid: "246764"
  - uid: "246778"
  - uid: "246782"
  - uid: "246783"
  - uid: "246793"
  - uid: "246794"
  - uid: "246838"
uid-files: "contribution/windowhandler-(vvvv)-files"
title: "WindowHandler (VVVV)"
image: "WindowHandler (VVVV) help-WindowHandler_2017.10.26-01.45.02.png"
contribution: "true"
---

**find, move, resize and arrange vvvv windows, and show them in the taskbar**

yet another long overdue release out of my vvvv helpers

1.  features
* gui window listing all currently opened vvvv windows
* list can be **filtered by types** (patch, renderer, gui and editors)
* **toggle** the ones you fancy to show up in the **taskbar**
* move selected ones via **keyboard shortcuts** (e.g. '1' to bring lost ones back to the primary screen)
* **pixelprecise** setting **position** and/or **size**, inner or outer size (e.g. you want a renderer to be exactly FullHD)
* **tile** selected ones over the current screen
* all gui elements have nice **tooltips** with usage hints

1.  details
on selection there are following shortcuts:
* 'F' to **focus**
* '1'...'9' to move to that **screen number** (retains size and relative position)
* arrow keys to **snap** to left/top/right/bottom of current screen
they will only be active if the GUI window was the last one to have focus. so it shouldn't be intrusive with actual application shortcuts or other vvvv interaction

when using the Set button and the number boxes for pixel precise settings leaving a box empty keeps that property untouched

tiling only works for windows which show up in the taskbar

###  quirks
<div class="box">
Note:
the **taskbar toggle is not persistant**. once you close/hide a window shown in the taskbar and reopen you'll have to set it again. would require some native vvvv rework to have that.

HDE host gives me **no** info about the **VL editor**, so no chance to handle that one.
</div>

you're welcome
