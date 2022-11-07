---
uid: "contribution/motion-blur-0"
uid-meta: "contribution/motion-blur-0-meta"
comments: 
 items: 
  - uid: "59459"
  - uid: "59461"
  - uid: "59462"
  - uid: "59465"
  - uid: "59469"
  - uid: "59470"
  - uid: "59481"
  - uid: "59503"
  - uid: "59505"
  - uid: "85763"
  - uid: "85766"
  - uid: "85771"
uid-files: "contribution/motion-blur-0-files"
title: "Motion Blur 2"
image: "MotionBlur (EX9 Texture Filter) help-DirectX Renderer_2012.07.17-03.50.41.png"
contribution: "true"
---

this reacts to world-, view-, projection-, aspect ratio transformation and dynamic meshes too.

the help patch is a bit lame but i hope that shows well how to use this.
have fun!:)

update:
i've done some minor fixes and cleanups and i solved the ugly edges by smoothing the velocity map. also i discovered that the blur of the movement on Z axis was incorrect when perspective was used so that's fixed too.

update2:
revamped the whole thing: now it's nicer and has more control. still it has some ghosts caused by the blur though.

update3:
added blur filter instead of the gaussianblur, added more control to velocitymaps, corrected this and that

update4:
i discovered after this long time that the direction of the blurring was not always right and it was annoying. so it's fixed now and it's way much nicer.