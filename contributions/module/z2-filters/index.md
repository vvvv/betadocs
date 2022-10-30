---
uid: "contribution/z2-filters"
uid-meta: "contribution/z2-filters-meta"
comments: 
 items: 
  - uid: "108558"
uid-files: "contribution/z2-filters-files"
title: "Z2 filters"
image: "Z2Filters.jpg"
contribution: "true"
---

It really surprised me, how you liked Z1 Filters, so I collected some more works for a new pack. There is:

**Background Substraction:** 
Green Screen shader. It's something like Trautner, but there are techniques to reuce camera noise. It splits still image (background) from new things (foreground)
It can be well used for Kinect background substraction.

**Triangulation:**
Is what you know from before. [triangulation-shader](xref:contribution/triangulation-shader)

**Blur Motion:**
This is improved Slow Down filter, now it blurs a bit each frame. You can add a lot of effects, just try to press "Add Glow" and see inside how simple is that.

**OSC Send Picture:**
If you ever needed to send a picture through OSC, it's possible. And there are few ways to do it. But none of them is correct... It goes on CPU, so possible resolution is low and CPU usage is high.

**SmoothStep:**
It's a function that makes a linear interpolation smooth. If you learn to use it, it's sooo great. <http://en.wikipedia.org/wiki/Smoothstep>
