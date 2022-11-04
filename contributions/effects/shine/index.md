---
uid: "contribution/shine"
uid-meta: "contribution/shine-meta"
uid-files: "contribution/shine-files"
title: "Shine"
image: "shine.jpg"
contribution: "true"
---

1. This isn't a ready to go effect but an example of how to achieve something like trapcode shine plugin (after effects)
2. the trick is simple! render your scene twice
3. first rendering contains your objects in front of the sun ( see gouraudshader in main patch)
4. second rendering contains your objects in front of the sun, rendered in black (see raynagator)
5. in the background of the black version is the 'sun' ....some blurry dot you can move
6. the whole image will then be radial blurred and later added (additive) to the first rendering
7. by moving the center of the radialblur and the position of your blurry object you can control the angle of the rays
8. have fun experimenting with this technique

note from tonfilm: it is also better to send only the blur of pass two to the third pass. for that, set includeorig to 0 and change the last line of the pixelshader to:

return includorig ? (c + tex2D(Samp, TexC.xy + Center))*factor : c * factor;