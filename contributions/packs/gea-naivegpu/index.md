---
uid: "contribution/gea.naivegpu"
uid-meta: "contribution/gea.naivegpu-meta"
comments: 
 items: 
  - uid: "270780"
  - uid: "270783"
  - uid: "270792"
  - uid: "270793"
  - uid: "270839"
  - uid: "270878"
  - uid: "271037"
  - uid: "271138"
  - uid: "271470"
  - uid: "271494"
  - uid: "275738"
  - uid: "276032"
  - uid: "276036"
  - uid: "278127"
uid-files: "contribution/gea.naivegpu-files"
title: "Gea.NaiveGPU"
image: "Gea.NaiveGPU.png"
contribution: "true"
---

###  VVVV.Gea.NaiveGPU
Naive physics simulation on GPU.
Rope and Cloth physics based on a simple Springs algorithm, verlet integration based.
An Euler GPU particles system can be managed within the same architecture
Particles, ropes and clothes can be created and managed separately.
Each entity of the system is called "group" (due to the fact that is a group of threads on the unique GPU buffer that holds all the data) (I know, I would call it differently now, but...).
You can apply forces, constraints and deformers to individual groups or to all of them together.

###  Disclaim
This is a software prototype born one year ago, built in crazy hurry for a project and full of compromizes and probably unfinished parts.
On one end I feel bit unconfortable in releasing it since nowadays I would sctructure it quite differently. It looks so imperfect to me...
..but on the other ends it contains some principles that might be interesting for other users. This is why i decided to publish it, in it's unperfect state, just adding some comments to the patches hoping it gets a bit more understandable. you can always ask me on the forum...
Ah, I didn't have really time to prepare nice help patches or multiple example scenarios. I just have one example patch in which you see most of the stuff at work...


###  Required packs
- dx11
- dx11.Particles
- Happy.fxh

###  Repository
If you would like to contribute to the development of the pack (adding help patches, modules,...) you can find it here:
<https://github.com/vvvv-dottore/VVVV.Gea.NaiveGPU>

Ciao

N
