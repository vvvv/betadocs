---
uid: "contribution/switching-preset-scenes-on-kramer-vp8x8"
uid-meta: "contribution/switching-preset-scenes-on-kramer-vp8x8-meta"
uid-files: "contribution/switching-preset-scenes-on-kramer-vp8x8-files"
title: "Switching preset scenes on Kramer VP8x8"
image: "Kramer-VP8x8-Switch_Preset_2013.03.07-20.10.34.png"
contribution: "true"
---

This patch implements the rs232 message to change between the first 8 pre saved I/O preset on VP 8x8 matrix.

In my case i had to switch 3 matrix at the same time. To avoid cascading them through rs 485 and setting the #machine I connect them all using individual ethernet cables and setup a virtual comm port for each one. Next time i will try to implement ethernet messages directly.

All the information and soft needed to set up the virutual comm ports and ethernet configuration is available at kramer page on this link:

<http://www.kramerelectronics.com/products/model.asp?pid=387&sf=47><>

NOTE: Im not shure if it will work if the matrix is configured in confirm mode.

My first contribution, bye.