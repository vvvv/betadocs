---
uid: "contribution/blackmagic-dx11-video-input"
uid-meta: "contribution/blackmagic-dx11-video-input-meta"
comments: 
 items: 
  - uid: "220383"
  - uid: "220384"
  - uid: "220495"
  - uid: "224710"
  - uid: "225763"
  - uid: "226823"
  - uid: "226972"
  - uid: "244314"
  - uid: "244623"
  - uid: "244984"
  - uid: "245267"
  - uid: "249837"
  - uid: "273952"
  - uid: "274190"
  - uid: "274211"
  - uid: "274455"
uid-files: "contribution/blackmagic-dx11-video-input-files"
title: "Blackmagic DX11 Video Input"
contribution: "true"
---

This is the DX11 version of the Blackmagic VideoInput nodes <https://vvvv.org/contribution/vvvv.nodes.decklink>, as discussed here [video-input-from-professional-digital-cameras](https://discourse.vvvv.org/t/video-input-from-professional-digital-cameras) and here [blackmagic-and-dx11-0](https://discourse.vvvv.org/t/blackmagic-and-dx11-0).

For reference:

<div class="box">quote:eno:
... But all in all this works, also with multiple cameras. We are going through SDI, but capturing HDMI should also be possible with the appropriate cards; we're using the Decklink SDI 4K cards.
The nodes are limited to HD at the moment though. The current videoIn Node doesn't list the 4k modes ... I bet it's not a big deal to add the 4k modes. The original BM capture software offers the 4k modes.
The other thing is that the c# wrapper that Blackmagic offers for their c++ library is cueing uo frames somewhere without really telling you. We've grown some grey hair over that problem already. This is introducing an uncertain delay of some frames, unless you reset the pipeline during runteime and make sure your v4 framerate doesn't drop below the video framerate; or move capturing to a separate instance.</div>