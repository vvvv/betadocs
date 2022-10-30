---
uid: "contribution/simplecloth"
uid-meta: "contribution/simplecloth-meta"
comments: 
 items: 
  - uid: "211585"
  - uid: "214114"
  - uid: "216891"
uid-files: "contribution/simplecloth-files"
title: "SimpleCloth"
image: "SimpleClothDemo01.png"
contribution: "true"
---

another fruit of the code cleaning fall 2015

1.  SimpleCloth
VVVV node set for a moduluar **cloth simulation** system

quickly hacked together for the visuals acompaning the [node15 symposium](http://node15.vvvv.org/program/wrapped-in-code-the-informed-body-symposium), frankfurt

by no means physically correct!

v 1.0:

* CreateCloth: init cloth plane
* GlobalForce: cloth properties, world force
* Attractor: spherical distortion
* LocalForce: force per vertex
* Pin: pin vertex to current position
* SetPosition: try set vertex position
* SetTarget: vertex target
* Evaluate: evaluate system
* Split: output all vertices
* Sample: get position on cloth plane
* AsTexture: output data as texture

nicely versioned here
<https://github.com/woeishi/VVVV.SimpleCloth>

<div class="box">
Note:
this contribution is CPU-based. if you need high performance cloth better check out [this one](xref:contribution/wrapped-in-code). it can probably do the same things. 
i just didn't have the time to get it running in time, therefore this set...
</div>
