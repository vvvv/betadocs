---
uid: "contribution/vvvv.audio-pack-alpha"
uid-meta: "contribution/vvvv.audio-pack-alpha-meta"
comments: 
 items: 
  - uid: "111856"
  - uid: "111859"
  - uid: "111864"
  - uid: "111865"
  - uid: "111875"
  - uid: "111885"
  - uid: "111921"
  - uid: "112014"
  - uid: "112015"
  - uid: "112804"
  - uid: "114266"
  - uid: "114534"
  - uid: "114537"
  - uid: "114588"
  - uid: "114734"
  - uid: "114742"
  - uid: "114752"
  - uid: "114759"
  - uid: "114812"
  - uid: "114833"
  - uid: "114856"
  - uid: "114904"
  - uid: "115252"
  - uid: "115264"
  - uid: "152790"
  - uid: "153383"
  - uid: "153390"
  - uid: "153391"
  - uid: "153409"
  - uid: "153449"
  - uid: "155206"
  - uid: "155405"
  - uid: "155439"
  - uid: "158995"
  - uid: "160433"
  - uid: "161167"
  - uid: "161179"
  - uid: "161236"
  - uid: "161252"
  - uid: "161254"
  - uid: "164054"
  - uid: "164067"
  - uid: "164085"
  - uid: "164116"
  - uid: "164128"
  - uid: "164169"
  - uid: "164374"
  - uid: "164390"
  - uid: "165302"
  - uid: "192309"
  - uid: "194270"
  - uid: "198742"
  - uid: "198769"
  - uid: "198826"
  - uid: "199933"
  - uid: "205437"
  - uid: "205443"
  - uid: "205500"
  - uid: "205755"
  - uid: "205766"
  - uid: "206101"
  - uid: "217210"
  - uid: "217224"
  - uid: "219360"
  - uid: "219401"
  - uid: "219405"
  - uid: "223650"
  - uid: "223680"
  - uid: "223841"
  - uid: "232443"
  - uid: "239438"
  - uid: "239439"
  - uid: "240828"
  - uid: "240829"
  - uid: "240832"
  - uid: "240836"
  - uid: "240851"
  - uid: "242344"
  - uid: "253606"
  - uid: "254351"
  - uid: "254369"
  - uid: "254379"
  - uid: "259863"
  - uid: "263251"
  - uid: "275615"
  - uid: "279819"
uid-files: "contribution/vvvv.audio-pack-alpha-files"
title: "VVVV.Audio Pack Alpha"
contribution: "true"
---

This is a vvvv audio engine.

<div class="box">
Note:
**VST plugins are platform specific**: if you use the pack with a 32-bit vvvv you can only host 32-bit VST plugins and the 64-bit vvvv can only host 64-bit VSTs.
</div>

Please report all bugs and feature requests here:
<https://github.com/tebjan/VVVV.Audio/issues/new>

NEWS:
- LTC timecode support sponsored by [meso](http://meso.net) based on [elliotwoods](http://vvvv.org/users/elliotwoods) work
- 64-bit support based on [bjoern](http://vvvv.org/users/bjoern)s branch
- FileStream got a <span class="pin">Speed</span> pin, also by courtesy of [meso](https://vvvv.org/businesses/meso)

There was no time to make proper help patches, but a few girlpower patches made it in the pack. I've also included the free sci-fi effects synth Altair 4b from [HGF-Synthesizers](http://hgf-synthesizer.com/nfg---pro-vsti-free.html) to demo the vst support.

For now, the focus of the engine was not so much DSP programming but flexible signal routing for large scale installations and VST support.
The new FileStream node can playback audio from the following formats:
[Supported Media Formats in Media Foundation](http://msdn.microsoft.com/en-us/library/windows/desktop/dd757927(v=vs.85).aspx)

Here are some more resources to check: [vvvv.audio-node15-workshop-patches](xref:contribution/vvvv.audio-node15-workshop-patches)

The world of VST is so huge and even for free, you can get almost anything you could wish for. Maybe you should have a look at sites like this one:

[bedroomproducersblog - Free VST Plugins by Category](http://bedroomproducersblog.com/free-vst-plugins/)

##  Discussion

A dedicated forums thread is here: [vvvv.audio-discussion](https://discourse.vvvv.org/t/vvvv.audio-discussion)

##  Installation

Copy the folder in the zip file into the vvvv folder (integrate if it exists). It works for both, 32 and 64-bit vvvv versions. See also: [using-addons](https://betadocs.vvvv.org/using-vvvv/patching/using-addons.html)

<div class="box">
Note:
In **beta39** you must delete the VVVV.Audio.Core.dll/pdb files in the 2 folders
 vvvv_beta_39_x64\lib\nugets\core
 vvvv_beta_39_x64\lib\nugets\VL.CoreLib.2019.1.0-0959-g3a31ab0c51\lib\net472
These files are build artifacts from VL, the issue will be fixed with beta39.1, sorry for the inconvenience.
</div>

You need to install [LoopBe](http://www.nerds.de/en/loopbe1.html) (tested with LoopBe1) and [Asio4All](http://www.asio4all.com/).

If you encounter problems loading the Jacobi.Vst.Interop.dll (e.g. all VSTHost nodes have nil in/outputs) you need to install:
[Visual C++ Redistributable for Visual Studio](http://www.microsoft.com/en-us/download/details.aspx?id=30679)

## Learning:

Here is an online workshop video which explains all the basic nodes and concepts, starting at 8m24s:
<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" data-src="https://www.youtube.com/embed/I2nnyRkbllo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

And a little demo video comes along:
<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" data-src="https://www.youtube.com/embed/VchIgx5jtns" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

And if you are interested in how to patch audio with VL, here you go:
<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" data-src="https://www.youtube.com/embed/neQLttKMEgg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

##  Change Log

* version 13 comes with a VL example, open "VL Test.v4p" in /girlpower
[GitHub closed issues](https://github.com/tebjan/VVVV.Audio/issues?state=closed)
[GitHub commits](https://github.com/tebjan/VVVV.Audio/commits/master)

##  Known Bugs

- VST Shells are not supported yet, but you can use shell2vst from Waves to extract the single plugins into dlls
- Buffer read/write behave strangely some times
- can click while patching