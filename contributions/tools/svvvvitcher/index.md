---
uid: "contribution/svvvvitcher"
uid-meta: "contribution/svvvvitcher-meta"
comments: 
 items: 
  - uid: "78062"
  - uid: "78124"
  - uid: "78161"
  - uid: "88056"
  - uid: "88066"
  - uid: "88107"
uid-files: "contribution/svvvvitcher-files"
title: "Svvvvitcher"
image: "_root_MAIN-gui_2009.05.22-04.52.59.jpg"
contribution: "true"
---

## why?

after three attempts to make a nice vj tool, i came to the conclusion, that the most powerful thing is to switch patches. because a patch can do just anything, it can contain videos, pictures, 3d models, generative stuff etc.. and... there are just thousands around. every vvvv patcher has lots of try outs, small ideas and whatever on his harddrive. wouldn't it just nice to drop them all into a folder and mix them on a vj set? sure it is!
<!--break-->
## what?

when makeing a patch audio reactive, you would usually use some audio analysis nodes, connecte them to some pins in your patch and add a few controllers for realtime modifications. and this is what svvvvitcher simply does, it provides a framework around your patches with audio analysis values and realtime controllers.

## how?

the only thing you have to do to add a patch to the svvvvitcher, is adding 5 IOBoxes, 3 inputs and two outputs:

* Control, input for the realtime controllers
* Audio Analysis, input for the audio analysis values
* Screen Resolution, input to let the patch know how the actual output screen resolution is, needed in case aspect ratio matters or on multi screen setups

* Texture Out, output of the rendered image of the patch
* Controller Names, output to give the svvvvitcher gui some infos what the realtime controllers do in the patch

then of course, you have to connect the IOboxes in your patch and add a <span class="node">DX9Texture (EX9.Texture) </span> node to render the output texture. After this you need to give the modified patch a name starting with "_root_" (this is necessary, to allow patches to load subpatches) and drop it sowmwhere into the 'Patches' folder of the Svvvvitcher. the svvvvitcher scans this folder for patches with that naming.

## features

* 2 patch channels
* 20 blend modes, order can be flipped
* up to 45 patches
* up to 42 post effect shaders
* 768 places to store presets
* texture preload
* midi learn
* midi out for controller feedback

a disadvantage is that vvvv has a short freeze when patches are switched, depending on the size of the patch. but in a vj set of many hours.. who really cares?

## requirements

in order to run svvvvitcher you need to have the addonpack and .NET 2.0 installed, as stated at the [downloads](https://vvvv.org/downloads) page.

## comments

a forum thread for svvvvitcher is [here](http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=26904&topics_threshold=0&topics_offset=0&topics_sort_mode=lastPost_desc&topics_find=&forumId=11).

## tools for svvvvitcher

Bank Svvvvitcher: A simple tool for reorder presets banks: [bankSvvvitcher.rar (12.81 Kb)](http://vvvv.org/tiki-download_file.php?fileId=1997) (by [drakko](http://vvvv.org/users/drakko%22+%22drakko) and r.arcaya)