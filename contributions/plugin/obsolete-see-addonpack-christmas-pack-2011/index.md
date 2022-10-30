---
uid: "contribution/obsolete-see-addonpack-christmas-pack-2011"
uid-meta: "contribution/obsolete-see-addonpack-christmas-pack-2011-meta"
comments: 
 items: 
  - uid: "74067"
  - uid: "74069"
  - uid: "74071"
  - uid: "74074"
  - uid: "74080"
  - uid: "74083"
  - uid: "74084"
  - uid: "74091"
  - uid: "74092"
  - uid: "74093"
  - uid: "74094"
  - uid: "74099"
  - uid: "74100"
  - uid: "74111"
  - uid: "74148"
  - uid: "74149"
  - uid: "74151"
  - uid: "74164"
  - uid: "74167"
  - uid: "74174"
  - uid: "74179"
  - uid: "74181"
  - uid: "74266"
  - uid: "74270"
  - uid: "74466"
  - uid: "74725"
  - uid: "74768"
  - uid: "81071"
  - uid: "81093"
uid-files: "contribution/obsolete-see-addonpack-christmas-pack-2011-files"
title: "[OBSOLETE, see Addonpack] Christmas Pack 2011"
contribution: "true"
---

Ok so here we go, this time of the year again and vvvv kids like toys.

So what's in the boxes this year:

* UGR File Parser: Just a little threat, reads fractal programs gradient files, good gradient alway handy to have
* Nearest Neighbours: In 1/2/3/4 d flavour, send some reference points, and finds nearest neighbour for any point you send.

Now after this little teaser, let's go for le "Plat de resistance" 

First, a set of nodes to access Kinect using Microsoft SDK.
Depth/RGB/Skeleton are supported.

Make sure you download: http://kinectforwindows.org/download/
(Please note that you must download the 64bits version if your OS is so, it still works in 4v).

Then, in collaboration with flateric, here is a new mesh loader.
It's still early version but it loads meshes (which is kinda useful for a mesh loader...) and allows you to access scene data. 
It's using the great library called assimp, for a list of native supported formats please look here:
http://assimp.sourceforge.net/main_features_formats.html

Still early stage, but look out for this one new features will arrive very quickly.

Now let's go for dessert, first public release for TodoMap.

TodoMap is a gui based Midi/Osc mapper. It supports a lot of features but basically create a variable, click a variable and learn mode, move a slider on your controller (or some touchosc control) and voila.

For all features would nee a user guide, but will let you play with it it's quite straightforward.

Few supported features:
* Integrated minimum/maximum/tweener for each variable
* Multiple inputs per variable
* Takeover mode per input (ableton style) eg: Immediate, Pickup (control need to reach the value), Value Scaling (Smooth convergence)
* Midi unplug/replug: no need to restart vvvv
* Automatic feedback (if your midi device supports it)
* Midi clock
* All settings saved to a simple xml file
* Preset nodes
* Values also controllable trough patch.

Please note you get a free Donut if you find why this node got called TodoMap :)

NOTE 1: Seems was midi bug, since some sanford dll were missing (thought they were all included in last release). New zip contains old folder and sanford libraries, copy those in vvvvroot/lib/core.


Format is same as in addon pack, so easy way to install is unzip and add:
xmaspack-2011\lib\nodes in root patch nodelist.

Have fun