---
uid: 268ce39d-8d40-41ed-bc01-e9e0a1e2587b
---

# DMX & Art-Net


<a href="http://en.wikipedia.org/wiki/DMX512" class="extURL" target="_blank">DMX</a>  
<a href="http://en.wikipedia.org/wiki/Art-Net" class="extURL" target="_blank">Art-Net</a>  
<a href="http://www.artisticlicence.com/WebSiteMaster/User%20Guides/art-net.pdf" class="extURL" target="_blank">Art-Net spicification</a>  

#### Related nodes
[node:ArtNet (Network Sender](TODO INTERNALLINK:node:ArtNet (Network Sender)  
[node:ArtNet (Network Receiver](TODO INTERNALLINK:node:ArtNet (Network Receiver)  
...and many more  




The DMX-protocol transmits up to 512 channels per universe, this is equivalent to a spread of 512 slices.  

DMX values are Integers in the range (0..255) but from vvvv you set them in a range of (0..1) instead. Keep in mind that the resolution is still 8-bit though, so only 256 steps (including 0 and 1) are possible.  

Art-Net is a standard for transmission of DMX over Ethernet.  

vvvv supports the Art-Net II specification with a total number of 256 universes: 16 subnets with 16 universes each.   

As defined in the protocol, Art-Net talks over UDP on port 6454 (0x1936). This port number can be changed: just start vvvv from a command line with an option '/artnetport nnnn' (nnnn - your port number).  

Examples in your vvvv\girlpower\ directory:  
* IO\DMX  

**See also:**  
* <a href="https://vvvv.org/contributions/1353+1351+2439+1352+7934+2438+1354+1355/7414+2187" class="extURL" target="_blank">Related Contributions</a>  
* [A range of DMX Modules](TODO INTERNALLINK:kalle.Modules.DMX) by <span class="user"><a href="https://vvvv.org/users/kalle" class="extURL" target="_blank">kalle</a></span>  
* [List of DMX Hardware](TODO INTERNALLINK:dmx.hardware)  
* [node08 DMX workshop material](TODO INTERNALLINK:node08.workshop.DMX)  




