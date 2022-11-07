---
uid: "contribution/ioscaler"
uid-meta: "contribution/ioscaler-meta"
comments: 
 items: 
  - uid: "95965"
  - uid: "207359"
uid-files: "contribution/ioscaler-files"
title: "IOScaler"
image: "IOScaler.png"
contribution: "true"
---

Change font size according to height of IOBox

As suggested by mrboni here:
[/forum/feature-request-scale-iobox-text-px-size-based-on-io-box-size](/forum/feature-request-scale-iobox-text-px-size-based-on-io-box-size)


how to use:
- place into root patch
- hold Shift while scaling an IOBox

limitations:
- only 1 box at a time
- does not take enumerations amount into account

bug:
- IOBox sometimes not movable after scaling
workaround:
- scale again without holding Shift
- to prevent this from happening start scaling first, then hold Shift

v.1.1

- can be placed into root patch now