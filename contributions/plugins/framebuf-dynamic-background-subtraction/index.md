---
uid: "contribution/framebuf-dynamic-background-subtraction"
uid-meta: "contribution/framebuf-dynamic-background-subtraction-meta"
comments: 
 items: 
  - uid: "102755"
  - uid: "269919"
uid-files: "contribution/framebuf-dynamic-background-subtraction-files"
title: "Framebuf - Dynamic Background Subtraction"
image: "framebuf.PNG"
contribution: "true"
---

a goodie from the past: this is a freeframe plugin i used to optimize video-tracking and filter static background.

just got it working with beta30 again. in order to do so you need to:

- copy framebuf.dll to vvvv_45beta30_x86\lib\nodes\freeframes
- copy the contents(opencv stuff) of system.zip to C:\Windows\system
- start vvvv and check helpfile

beware, it might not work with resolution higher than 640x480

if you want to make an opencv 2.0 version or something better, the zip contains the code