---
uid: "contribution/osc-plugin"
uid-meta: "contribution/osc-plugin-meta"
comments: 
 items: 
  - uid: "72918"
  - uid: "82968"
uid-files: "contribution/osc-plugin-files"
title: "OSC plugin"
contribution: "true"
---

Simple set of OSC nodes:

* <span class="node">Client (OSC)</span>
* <span class="node">Server (OSC)</span>

* <span class="node">R (OSC)</span>
* <span class="node">S (OSC)</span>

* <span class="node">Count (OSC)</span>
* <span class="node">AsValue (OSC)</span>
* <span class="node">Sift (OSC)</span>

* <span class="node">Receive (OSC Bang)</span>
* <span class="node">Receive (OSC String)</span>
* <span class="node">Receive (OSC Value)</span>
* <span class="node">Send (OSC String)</span>
* <span class="node">Send (OSC Value)</span>

* <span class="node">R+H (OSC LTP)</span>
* <span class="node">R+H (OSC String)</span>
* <span class="node">R+H (OSC Value)</span>

Main features
* OSC channels are global (generally no need for links or R/S nodes except for to attach a server/client to a channnel. Just denote the channel name, defaults are 'Tx' = send from VVVV, and 'Rx' = Receive to VVVV)
* R+H node keeps a local register of inputs
* Multiple Send nodes don't need any special treatment (cons, whatever).
