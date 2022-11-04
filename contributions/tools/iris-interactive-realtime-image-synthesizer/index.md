---
uid: "contribution/iris-interactive-realtime-image-synthesizer"
uid-meta: "contribution/iris-interactive-realtime-image-synthesizer-meta"
comments: 
 items: 
  - uid: "82455"
  - uid: "82468"
  - uid: "82473"
  - uid: "82496"
  - uid: "82511"
  - uid: "82531"
  - uid: "82540"
  - uid: "82564"
  - uid: "82655"
  - uid: "82656"
  - uid: "82666"
  - uid: "82673"
  - uid: "82675"
  - uid: "82690"
  - uid: "82785"
  - uid: "83618"
  - uid: "84572"
  - uid: "84573"
  - uid: "84695"
  - uid: "84830"
  - uid: "84834"
  - uid: "84854"
  - uid: "84889"
  - uid: "84936"
  - uid: "85006"
  - uid: "86330"
  - uid: "86405"
  - uid: "86457"
  - uid: "86476"
  - uid: "88116"
  - uid: "103572"
  - uid: "103586"
  - uid: "218547"
  - uid: "218613"
  - uid: "218617"
  - uid: "218620"
  - uid: "218976"
title: "IRIS - Interactive Realtime Image Synthesizer"
image: "Iris_pc.jpg"
contribution: "true"
---

**The versions of IRIS on this website are outdated and no longer supported.**
****
__Were still working on IRIS using it for professional production since years. As there is no public version at the moment -please get in touch if you need the flexibility of working with vvvv on site combined with a reliable, frame accuracy playback system. 

---
This was the first public release of a performance framework we had have developed during several projects over the past years. It is (of course!) not finished and can be improved in many ways. We chose to make it public at this point to discuss its concepts with a larger user and developer base - and we hope that it proves to be useful for your projects. 

In comparison to other v4-patch-changing approaches out there we have put a strong focus on a flexible, touchable interface and scalable in- and output. So far IRIS has proven its usability in several venues and events such as the CocoonClub, the Coke Happiness Monument or the INTEL visibly smart tour.
   
###  Download 
<https://bitbucket.org/nsynk/iris_v0.1_legacy> additional credits: avienhoe

<https://bitbucket.org/nsynk/iris_v0.2_legacy>

   
###  IRIS is based on these Concepts:
**Texturebased**
Textures are the only Information shared between modules

**What you see is what you get**
Every step of the image synthesis is visible on the screen

**Flexible Interface**
Every patch defines the interface it needs. No limitations in number and type of parameters

**Sequencer**
Value parameters can be animated and recorded as quantized sequences

**Server-Client System**
Change patches in a server-client environment (no Boygroup). This allows for large scale realtime renderings and performances with redundant servers and great failure safety.

**Multi-User**
Collaborate on a show with many interfaces simultaneously

**Signals**
Create your own Signal Generators and route them to any parameter. MIDI and OSC input handled flexible by Signal generator modules

**Library**
Fast browsable media library for textures, models, v4patches and bundles

**Touch Interface**
Optimized Interface for touch input

**V4 Bundle**
No interdependencies between modules and directory structures

 
###  How to get started
Download IRIS from the Bitbucket project page.
Start beta 27.1 and run install.v4p from the IRIS directory.
Run startMasterInterfacePerformance.cmd
Now you should have IRIS running with a couple of demo modules and library items installed that came with the download.

Per default the ‘Master’ menu item needs to be blue and the small N (for Network) toggle has to be switched off. Other settings are needed for Server-Client setups and for multiple interfaces.

Now you can ‘Load Patch’ to change the modules. Alter the parameters by clicking on them. Clicking on a string parameter brings up the library. Hold spacebar to record animations. Open the signals pane to map signals.

To make your own modules look into the Interface Root/Screencontainer4/Sandbox.v4p patch. The Sandbox resembles the signal path of the Interface. Open the respective Generator, PostFX or Mixer patches. You can see how to set up a content module. Be sure not to change the In- and Output Pin Names.

Signal Generators are for now the patches loaded in the Signalbay, and cannot be changed thr. These patches do the audio-analysis, MIDI- and OSC-Input (or any other protocol) or provide custom shaped signals. 

Put your own modules into IRIS/library folder and be sure to meet the ‘v4bundle’ naming conventions (a v4bundle is patch in a folder of the same name, that contains all the resources needed to run the patch). Also add your media to the library. You can make your own folder structure to organize your library. Thumbnails will be created automatically when you press ‘update library’ in the library screen. Thumbnails for patches have to be created manually and be part of the v4bundle as thumbnail.png.
   
###  Known Issues
**Update all**
if a patch is changed on a machine by an 'update all' instruction, the new patch will get its values only after update all is executed a second time.

**Save Set**
Recorded sequences are not saved / loaded
   
   
   