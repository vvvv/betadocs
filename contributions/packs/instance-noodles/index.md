---
uid: "contribution/instance-noodles"
uid-meta: "contribution/instance-noodles-meta"
comments: 
 items: 
  - uid: "204963"
  - uid: "204968"
  - uid: "204969"
  - uid: "204975"
  - uid: "204979"
  - uid: "204986"
  - uid: "205002"
  - uid: "205015"
  - uid: "205021"
  - uid: "205045"
  - uid: "205057"
  - uid: "205063"
  - uid: "205193"
  - uid: "205231"
  - uid: "205433"
  - uid: "205501"
  - uid: "205641"
  - uid: "206192"
  - uid: "206280"
  - uid: "206367"
  - uid: "206381"
  - uid: "206388"
  - uid: "206409"
  - uid: "206490"
  - uid: "206901"
  - uid: "206922"
  - uid: "206938"
  - uid: "206973"
  - uid: "206999"
  - uid: "207022"
  - uid: "207026"
  - uid: "207128"
  - uid: "207178"
  - uid: "207203"
  - uid: "208605"
  - uid: "208614"
  - uid: "209613"
  - uid: "209877"
  - uid: "209910"
  - uid: "209938"
  - uid: "209977"
  - uid: "209989"
  - uid: "209991"
  - uid: "210013"
  - uid: "210044"
  - uid: "210075"
  - uid: "210080"
  - uid: "210083"
  - uid: "210138"
  - uid: "210140"
  - uid: "210158"
  - uid: "210160"
  - uid: "210177"
  - uid: "210206"
  - uid: "211482"
  - uid: "211495"
  - uid: "211545"
  - uid: "211547"
  - uid: "211890"
  - uid: "211912"
  - uid: "213328"
  - uid: "216776"
  - uid: "219346"
  - uid: "223382"
  - uid: "223385"
  - uid: "223683"
  - uid: "225771"
  - uid: "226158"
  - uid: "226477"
  - uid: "232646"
  - uid: "232674"
  - uid: "232969"
  - uid: "239686"
  - uid: "239745"
  - uid: "243017"
  - uid: "243026"
  - uid: "243087"
  - uid: "245467"
  - uid: "245480"
  - uid: "248074"
  - uid: "248870"
  - uid: "249170"
  - uid: "249207"
  - uid: "249222"
  - uid: "249268"
  - uid: "249292"
  - uid: "250028"
  - uid: "250029"
  - uid: "250032"
  - uid: "253383"
  - uid: "253599"
  - uid: "256726"
  - uid: "256732"
  - uid: "256786"
  - uid: "256877"
  - uid: "256881"
  - uid: "256897"
  - uid: "257360"
  - uid: "257396"
  - uid: "257410"
  - uid: "265354"
  - uid: "268312"
  - uid: "270377"
  - uid: "270494"
  - uid: "270624"
  - uid: "270861"
  - uid: "271009"
  - uid: "271174"
  - uid: "271175"
  - uid: "276807"
uid-files: "contribution/instance-noodles-files"
title: "Instance Noodles"
image: "Fresh_ramen_noodle_001.jpg"
contribution: "true"
---

Alpha 0.4 Tsukemen

Instance Noodles is a modular patching system for Compute & Geometry shaders in DX11/vvvv. Inspired by the fast & pleasant workflow in stock vvvv this lib aims to bring the same visual flow programming approach to GPGPU calculations & procedural geometry manipulation.

In 0.4 there are some new nodes, eg Subdivision (DX11.GeomFX), compute Zips, a nice LineBuffered(DX11.Layer) module (courtesy of Dávid “Microdee” Morass) and some general improvements such as adding a (hidden) thread group size pin and modernizing the default group size to 128 on all compute nodes.  +Quite a few other bits & bobs I’m too lazy to list.  Note that the pack now depends on ‘happy.fxh’ to be next to it in /packs in order to work.

Requires 

  •vvvv >= 35.7 + Addon Pack
  
  •DX11 pack >= 1.1
  
  •https://github.com/everyoneishappy/happy.fxh
  
  •a GPU that supports Shader Model 5
  
To install everything via VPM: https://vvvvpm.github.io/#InstanceNoodles
To install manually just place in /packs folder.  
For more frequent updates, bug fixes and issue reporting: https://github.com/everyoneishappy/InstanceNoodles

Substantial amounts of code borrowed from Vux, UNC, Microdee et al. If there is something that should be credited that's not just let me know.

MIT License- feel free to use in your creative & commercial projects.  If used in production a credit is very appreciated:

Kyle McLean / <http://everyoneishappy.com>

I’m also very happy if you are doing something interesting and want to employ me on a project basis.
