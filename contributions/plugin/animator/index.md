---
uid: "contribution/animator"
uid-meta: "contribution/animator-meta"
comments: 
 items: 
  - uid: "196279"
  - uid: "196361"
  - uid: "196385"
  - uid: "196805"
  - uid: "197175"
  - uid: "198984"
uid-files: "contribution/animator-files"
title: "Animator"
image: "animator_ico.png"
contribution: "true"
---

Pack of nodes for fast animation patching:

* **Animator**
Base logic for every tween with delay, repeat, seek, pause, etc. Fully spreadable and sync with internal timer. Replaces many animation nodes in one. Inspired by Zeh Fernando ([zeh](http://vvvv.org/users/zeh) ) <span class="node">tweener-(value)</span>.
* **Ease**
One node with easing presets (include google's swift  <http://www.google.com/design/spec/animation/authentic-motion.html>), one for custom easing function.
* **Lerp**
Makes interpolation between value/spline/color/transform.

###  Update
**v1.9**
* Fix start & repeat pins banging only when delay finished

Submit bugs and requests to:
https://github.com/gumilastik/VVVV.Animator