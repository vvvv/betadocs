---
uid: "contribution/spoutcontrols"
uid-meta: "contribution/spoutcontrols-meta"
comments: 
 items: 
  - uid: "226017"
  - uid: "226065"
  - uid: "226070"
  - uid: "226490"
  - uid: "226493"
  - uid: "226533"
uid-files: "contribution/spoutcontrols-files"
title: "SpoutControls"
image: "SpoutControls.jpg"
contribution: "true"
---

this is a small modification of the spout sender node, which can be found in the latest alphas. spout let's you share textures between vvvv and other freeframe hosts (eg resolume), this modification will let you control your patches from that host!
 
 
 
    
 

####  Supported control types: text, slider, toggle, press
####  To use it 
- download http://spout.zeal.co/download-spoutcontrols/ and install
- open this plugin's help patch
- name your sender and define your controls
- click <span class="pin">write</span>, this will create a text file describing the controls in C:\ProgramData\Spout
- refer to the pdf in C:\Program Files (x86)\SpoutControls on what to do with that txt for different hosts (for resolume, see below)
- every time you now start a patch containing the plugin with the same sender name and same number of controls a connection can be established, ie texture will be shared + values will be retrieved. just click <span class="pin">write</span> again.

resolume specific:
- in your resolume video plugin folder make a folder named vfx/*mysendername*
- copy the file *mysendername*.txt (created in the steps above) from C:\ProgramData\Spout to vfx/*mysendername*
- copy *SpoutController.dll* from C:\Program Files (x86)\SpoutControls\FREEFRAMEGL to vfx/*mysendername*
- (repeat for multiple sources)
- *mysendername* now should show up in resolume as source, drop it in a layer
- start the patch where you have defined the controls, hit <span class="pin">write</span> again and start sharing texture + receiving values!
note: SpoutController.dll will also try to start an executable *mysendername*.exe inside vfx/*mysendername*; so you could also copy a full vvvv into vfx/*mysendername* and rename vvvv.exe (+corresponding files) to *mysendername*.exe. a soon as you drop it in a layer vvvv will start, if you clear it vvvv will be closed. pretty neat, but maybe not too feasible for a high amount of animations. Maybe *mysendername*.exe could only open a v4p in a (certain(!) instance of an) already open vvvv, I might try that at some point.....

 
 
  
  
<div class="box">
Note:
NO 64 bit VERSION ATM (vvvv will crash)....while it should work in theory, i'm not sure what's wrong.... maybe a more experienced coder can have a look....in the meantime i'll keep trying....
</div>


 
 
 
####  Source code can be found here:
the c++ dll which calls spoutControl and exports functions to be called from vvvv:
https://github.com/digitalwannabe/SpoutControls4vvvv
the vvvv plugin:
https://github.com/digitalwannabe/vvvv-sdk/tree/develop/vvvv45/addonpack/src/nodes/plugins/System/SystemSpoutSender
 
 
####  Licenses:
Spout is Simplified BSD licence. My code is MIT.



Please note again: no guarantees; do not copy any of my code unless you know better and only use plugin in production after enough testing!


@devvvvs: as this is just add-on functionality to the spout sender, which does not change anything of the basic features, it would be ideal to incorporate this into the original spout sender node, maybe with a config pin to turn in it on/off....no need for 2 different sender nodes I would argue....would need some code improvement/cleanup though i guess ;)


thanks to [leadedge](http://vvvv.org/users/leadedge) for the great support!




