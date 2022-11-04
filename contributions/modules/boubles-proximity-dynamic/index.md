---
uid: "contribution/boubles-proximity-dynamic"
uid-meta: "contribution/boubles-proximity-dynamic-meta"
comments: 
 items: 
  - uid: "82362"
  - uid: "82397"
  - uid: "82400"
uid-files: "contribution/boubles-proximity-dynamic-files"
title: "Boubles Proximity Dynamic"
image: "BoublesProximityDynamic (2d Spreads) help Thumbnail.jpg"
contribution: "true"
---

This is an old patch i did studying **circles collision**. 
I upload it for documentation and for educational reasons; if you are looking for proper 2d rigid bodies simulation have a look at Vux's Box2d plugins.

Inside the patches you will find also the module **ProximityDynamic (2d Spreads)**. 
This module is usefull when you have a large number of interacting agents: it's a grid based proximity detection that gives, for each agent-particle, only the indices of neighbour agents (this means optimization in interaction evaluation).