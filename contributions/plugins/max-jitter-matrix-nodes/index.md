---
uid: "contribution/maxjitter-matrix-nodes"
uid-meta: "contribution/maxjitter-matrix-nodes-meta"
comments: 
 items: 
  - uid: "97470"
uid-files: "contribution/maxjitter-matrix-nodes-files"
title: "Max/Jitter Matrix Nodes"
image: "jitter_nodes.png"
contribution: "true"
---

1.  Max/Jitter Matrix Encoder and Decoder
Two nodes that try allow for exchange of Jitter matrix data between Max/MSP/Jitter and VVVV via TCP.

Essentially they are emulating the [jit.net.send](http://cycling74.com/docs/max5/refpages/jit-ref/jit.net.send.html) and [jit.net.recv](http://cycling74.com/docs/max5/refpages/jit-ref/jit.net.recv.html) nodes in Max.

##  Usage
###  VVVV to Max
Open helppatch of<span class="node">Jitter Matrix Encoder (Raw)</span> in VVVV and <span class="node">jit.net.recv</span> in Max. Set correct IPs (or localhost) and ports. The Encoder takes a spread of colors and the correct dimensions of the matrix need to be set. Enable TCP and bang <span class="pin">Do Send</span>.
###  Max to VVVV
Open helppatch of <span class="node">Jitter Matrix Decoder (Raw)</span> in VVVV and <span class="node">jit.mat.recv</span> in Max. Set correct local port in VVVV and correct IP/port in Max. Enable TCP node and wait for incoming data.

###  ToDo:
* decoding matrices of dimension count > 50x50 might result in memory problems

Feedback welcome!
####  Release 0.2
* added support for decoding arbitrary number of planes
* the download here is a binary release, sources can now be found [here](https://github.com/mhusinsky/VVVV.nodes.Jitter)

####  Release 0.1
* Still needs heavy testing
* Works only for one or two-dimensional matrices of type 0 (char/byte) with 4 planes (i.e. RGBA colors). 
* no messaging support yet
* timestamp not yet correct
* This is a binary release. Source release coming soon...

<div class="box">
Work commissioned by 
[Institute for Creative\Media/Technologies](http://icmt.fhstp.ac.at)
University of Applied Sciences St.Pölten, Austria</div>