---
uid: "contribution/player-(dx11.texture)"
uid-meta: "contribution/player-(dx11.texture)-meta"
comments: 
 items: 
  - uid: "213009"
  - uid: "213017"
  - uid: "213081"
  - uid: "220522"
  - uid: "221064"
  - uid: "221067"
  - uid: "224007"
  - uid: "238317"
  - uid: "238319"
  - uid: "241976"
  - uid: "242408"
  - uid: "242409"
  - uid: "247132"
  - uid: "247651"
  - uid: "247652"
  - uid: "247676"
  - uid: "247730"
  - uid: "247731"
  - uid: "247732"
  - uid: "247811"
  - uid: "247820"
  - uid: "247825"
  - uid: "247889"
  - uid: "247890"
  - uid: "247900"
  - uid: "247901"
  - uid: "261290"
  - uid: "271361"
  - uid: "271422"
uid-files: "contribution/player-(dx11.texture)-files"
title: "Player (DX11.Texture)"
contribution: "true"
---

**first off:** send massive thanks to [meso](http://meso.design) for sponsoring the development and even more for making it public! now again for supporting a major update.

1.  Player (DX11.Texture 2d)
## what's the deal?
if the nodename alone doesn't ring a bell: 
<div class="box">
optimized playback of picture stacks
1. asyncronously reads the file into RAM
1. asyncronously decodes if necessary
1. swaps the image to GPU and decodes if necessary</div>


tried a direct port of <span class="node">Player (EX9.Texture)</span> by [Elias](http://vvvv.org/users/Elias) but failed due to reasons. 
## so what's the **differences**: 
* tries to read any file, since it tries to pick up any codec of the OS
* doesn't parse the directory async
* extra debug output decoding time
* not tested with multiple graphicscards

## Change Log
###  2.0
huge rework of the reading and loading pipeline
* got rid of the slimdx call, which would allocate memory (and thus cause leaks on stuttering systems)
* GPU loader speedup x4 on my dev machine
* CPU backend now uses WIC instead of system drawing. 50% speedup
* removed restrictions on filetypes by file extension: will try to load and decode anything
* compacted reading+decoding: removed one debug timing output
* added pin to manually chose the decoder: file format support overlaps between sharpdx and wic and on some formats it depends on your system, which one is actually faster.
* wait for frame option, defaults to true: option off means, just show whatever is currently loaded, can result in showing frames more multiple times or skipping ones but wont block the mainloop at all
* reading and loading of files has higher priority than disposing and freeing memory. 

###  1.1
compatible from vvvv beta35.2 and dx11 1.0 onward
* upgrade to dx11 new interfaces as of dx11 pack 1.0 and .net 4.6 ([pullrequest](https://github.com/woeishi/VVVV.DX11.Player/pull/1) by MrRoundRobin)
* fixed output spreadcount not considering all input pins
* can handle negative indices properly (exception surfaced when using timebased module)

###  1.0
initial upload for vvvv version 33.7 + according dx11 pack  

---

[src on github](https://github.com/woeishi/VVVV.DX11.Player)

