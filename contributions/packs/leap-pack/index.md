---
uid: "contribution/leap-pack"
uid-meta: "contribution/leap-pack-meta"
comments: 
 items: 
  - uid: "162999"
  - uid: "163089"
  - uid: "167786"
  - uid: "168003"
  - uid: "171164"
  - uid: "172301"
  - uid: "172733"
  - uid: "175231"
  - uid: "175328"
  - uid: "196381"
  - uid: "196450"
  - uid: "196503"
  - uid: "196717"
  - uid: "196942"
  - uid: "197226"
  - uid: "207382"
  - uid: "217200"
  - uid: "217201"
  - uid: "273666"
  - uid: "273668"
  - uid: "273670"
  - uid: "273671"
  - uid: "273674"
  - uid: "273680"
  - uid: "273681"
  - uid: "273698"
  - uid: "273703"
uid-files: "contribution/leap-pack-files"
title: "Leap Pack"
image: "screenshot1408656711_0.png"
contribution: "true"
---

These nodes use the 2.1 and newer sdk of Leap with nearly all features it can have in an alternative approach to the current Leap implementation.

Installation: put it in the packs folder
Instructions: start girlpower.v4p

new:
- both for x86 and x64
- now frames can be managed individually
- which means you can retrieve earlier frames too
- which also means you can serialize it
- which again means you can save it to disc or send it over udp/tcp/sharedmemory/etc.
- saving to disc part: now there's a Record/Player module pair
- and finally: raw images! (which however doesn't get serialized :( )