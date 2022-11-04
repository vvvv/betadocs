---
uid: "contribution/particles-unplugged"
uid-meta: "contribution/particles-unplugged-meta"
comments: 
 items: 
  - uid: "107054"
  - uid: "107059"
  - uid: "107060"
  - uid: "107061"
  - uid: "107063"
  - uid: "107065"
  - uid: "107068"
  - uid: "107078"
  - uid: "107084"
  - uid: "107087"
  - uid: "107088"
  - uid: "107102"
  - uid: "107488"
  - uid: "107491"
  - uid: "107505"
  - uid: "108360"
  - uid: "108453"
  - uid: "110434"
  - uid: "110436"
  - uid: "110438"
  - uid: "110442"
  - uid: "110446"
  - uid: "110468"
  - uid: "110545"
  - uid: "165188"
  - uid: "165229"
  - uid: "165273"
uid-files: "contribution/particles-unplugged-files"
title: "Particles Unplugged"
image: "Nadpis.jpg"
contribution: "true"
---

Bug is dead, PS Unplugged is alive and **working now**. 
(You need [directx11-nodes-alpha ](xref:contribution/directx11-nodes ) )


The meaning of this particle system is to split the DX11 Particles in parts: Particle Emition, Particle Animation and Drawing the particles. To set a "standard" what these parts should do, so that we can freely combine them together. You can blend modules in real time to change your PS. 


It's like Vvvv concept. One can make a module of placing particles on a mesh. Another one can make collision of particles with depth of Kinect , or render this in blobs, add a material and finally somebody else can come and simply combine these parts with different ones. 


How the idea came up: Just on a NODE festival I spoke to Vux about an idea of this particle system where every force is added as a single node. He answered that it was his initial idea too, but he realised there is a performance loss, so that's not a good idea. What I thought was "that's great, it was his idea too" :) and started working on it. Now it's only few forces, so performance should be the same. There are some bugs, of course. Like a weird blinking if you put small lifetime.


P.S.: I'm a freelancer, so often unemployed. And can't keep working for "thanks, nicely done". Seriously, not good, wanted to quit Vvvv already and many friends told me to. If you think you could use my skills, send me an email: martin@probenesov.cz or visit <a href="http://martinzrcek.cz/en/">portfolio</a>