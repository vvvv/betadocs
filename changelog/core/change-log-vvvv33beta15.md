---
uid: 4ceb1238-163a-47b1-af33-71d0b8ed00fe
---

# Change Log - vvvv33beta15
released on 26 03 08  

## new boygrouping

* patches are transfered to the client as patches, not as a big unstructured graph like before.  
* it should be save to run an existing boygroup project.  
* you now can inspect the received patches on the client like you would inspect patches on your local machine (inspector, tooltip...). (however for now you shouldn't change received patches)  
* relative paths to resources now find their way, if the client and server directories for the project are identical. you now can structurize your work:  
  * you can place your resources - like effects, textures, xfiles - where they belong to: in your project directory, not in the vvvv directory.  
  * also patches now can be placed in different folders within your project directory.  
* nodes like setpatch, getpatch, patchalias, self (...) now make sense on the client too, since the client executes them within a patch   
* bounds of windows are transfered. in that way you can make sure that a renderer pops up on the second monitor of a client. this is good for situations when you want the first monitor to be used as kind of windows console with taskbar and windows startup screen, and a second monitor for the projection.  
* quiet mode (node Boygroup (VVVV Server)) should work even more quiet. you now can work with more people on the same project within the same LAN with several servers, but with only one communicating to the clients.   
* server and clients can be started in any order  
* synchronized pins (bridges) are faster than before  
* bridges can be inspected in the debug mode (CTRL-F9) on server and client. you see which pins send their value regularly and which bridges are inactive (yellow .. black depending on activity)  
* active and overall bridge counts can also be inspected through the new output pins on the Boygroup (VVVV Server) node.  
* log messages are created when "Broadcast Mode" is UDP, but some spreads are to big for UDP and therefore sent over TCP. good for debugging