---
uid: "contribution/slitscan-ringbuffer-(dx11)"
uid-meta: "contribution/slitscan-ringbuffer-(dx11)-meta"
comments: 
 items: 
  - uid: "102609"
  - uid: "102624"
  - uid: "102880"
uid-files: "contribution/slitscan-ringbuffer-(dx11)-files"
title: "Slitscan & Ringbuffer (DX11)"
image: "slitscan_0.PNG"
contribution: "true"
---

A ringbuffer in a volume texture and an appropriate texture-based slitscan shader.

I've been on a long journey, seeking an appropriate way to do texture-based slitscan deformations. 

I was a bit inspired by James George, who did (cpu-based) slitscanning in OF and finally had the idea to utilize a volume texture. Elektromeier did a related thing [here](elektromeier-khronosprojector) like about 8 years (!!) ago. That one was helpful, but still lacking the generation-part.

read this thread for more information: [texture-queue-in-a-volume-texture-%28dx11%29](https://discourse.vvvv.org/t/texture-queue-in-a-volume-texture-%28dx11%29)