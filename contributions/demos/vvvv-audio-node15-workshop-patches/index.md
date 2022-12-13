---
uid: "contribution/vvvv.audio-node15-workshop-patches"
uid-meta: "contribution/vvvv.audio-node15-workshop-patches-meta"
comments: 
 items: 
  - uid: "196553"
  - uid: "196565"
  - uid: "196576"
  - uid: "196577"
  - uid: "218920"
  - uid: "218954"
  - uid: "218957"
  - uid: "218967"
uid-files: "contribution/vvvv.audio-node15-workshop-patches-files"
title: "VVVV.Audio NODE15 Workshop Patches"
image: "VideoToSound_2015.05.21-20.53.19_0.png"
contribution: "true"
---

This is the material used in the VVVV.Audio workshop at NODE15. Download the audio nodes here: [vvvv.audio-pack-alpha](xref:contribution/vvvv.audio-pack-alpha)

The workshop was divided into two sections, the first part was about generative audio and the second about interactive installations and audio mixing with VST effects.

Since many people asked about the technique, the download also contains the patch that generates sound directly from a video texture.

The files in the download are only the patches since it is not allowed to redistribute the VST plugins even if they are free. But here is a list of all VST plugins recommended. By compiling the list it was important that all plugins are available in 32 and 64 bit.

##  Instruments

Starting at the beginning of the signal chain, VST intruments:

###  Sampler

A sampler is the tool of choice when it comes to sound files. Be it entire orchestra instrument libraries or just a simple one-shot 'bling' when a button is pressed. It is also recommended over the FileStream (Vaudio) node since it can load audio files in all sample rates and play them back in high quality in any mode (slow, fast, pitched, backwards, loop, ...).

This sampler was for me the most intuitive to work with, especially the automation is very cool to set up and its available for free in 64 and 32 bit:
http://www.onesmallclue.com/plugin/grace/

<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" data-src="https://www.youtube.com/embed/DA_c21vd0K4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

This is also a full featured sampler and also recommended:
http://www.tx16wx.com/

See this thread on how to use it in vvvv: [VAudio, saving VSTHost settings](https://discourse.vvvv.org/t/vaudio-saving-vsthost-settings/16358/6?u=tonfilm)

This video gives some workflow tipps, you can ignore the garage band stuff and start at 1:30
<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" data-src="https://www.youtube.com/embed/AZF2Jc-MaVE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


###  Synths

Synthesizers generate artificial sounds using mathematical algorithms. There are hundreds available, and the synths from u-he are definitely among the best. And luckily they offer free ones, these two are highly recommended:

http://www.u-he.com/cms/zebralette
http://www.u-he.com/cms/tyrelln6

These are also widely used and famous because of their great sound quality:
http://www.greenoak.com/crystal/dnld.html (has a genetic algorithm to 'breed' new sounds)
http://www.geocities.jp/daichi1969/softsynth/ (Synth1 is THE freeware synth, simple and low on CPU)

If you are unfamiliar with synth controls, here is a guy actually explaining every control of Synth1
<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" data-src="https://www.youtube.com/embed/CnAuhj2schY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

##  Effects

Audio effects are even more versatile than instruments. There are basic sound sculpting tools like equalizer and compressor as well as more 'creative' effects. This list focuses on the basics.

###  Packs

Effect packs are convenient downloads which contain all the basics for your effects chain. Usually you'd start with a compressor followed by an EQ...

http://www.reaper.fm/reaplugs/ (very recommended, high quality and precise EQ and compressor)
http://www.meldaproduction.com/plugins/product.php?id=MFreeEffectsBundle (biggest pack, EQ with realtime analyzer overlay as in the video below and helpful tools like file recorder, signal generator, ...)
http://www.gvst.co.uk/packages.htm (all the basics with simple controls)
http://www.bluecataudio.com/Products/Bundle_FreewarePack/ (honorable mention, looks sexy)

This is why an EQ is the most important effect in your signal chain:
<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" data-src="https://www.youtube.com/embed/kSNYBbPAvKE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

###  Compressor

Sometimes you don't want a very neutral and precise compressor as the ReaComp from the ReaPlugs pack, but you want to give your drumset or your bassline some fattness and character. then one of the following compressors will give you quite some pleasure.

http://www.tokyodawn.net/tdr-kotelnikov/ (very modern, clean and powerfull compressor)
http://klanghelm.com/DC1A.php (simple controls and adds nice punch to drums)
https://vladgsound.wordpress.com/plugins/molot/ (simulates old analog hardware, provides a nice character)

This video explains compressors super well. It uses a commercial plugin as an example but the controls are basically the same on all compressors. Watch it!
<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" data-src="https://www.youtube.com/embed/RkeJqtJGn0I" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

###  Reverb

We are always surrounded by spaces and all sound we hear gets reflected in one way or the other. This is what a reverb effect simulates, it gives a sound a space in which it lives. In that way it makes it more natural to our ears. There is usually one reverb which is used to put the individual tracks of a musical piece together in one space, as if they were played in the same room. See the send effect in the ChannelStrip.v4p patch. Exceptions are low frequency sounds like bass and kick drum which usually get no reverb, and drums which mostly have their own short reverbs.

http://kunz.corrupt.ch/products/tal-reverb (TAL-2 is a very famous freeware reverb)
http://www.voxengo.com/product/oldskoolverb/ (another high quality reverb for softer sounds)

Here is a quick intro into reverberation:
<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" data-src="https://www.youtube.com/embed/a1o6fZyDn2M" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

###  Limiter

The limiter is usually the last stage of your signal chain and sits right before the master output. It's like a watchdog that takes care of short peaks in the audio which would create clipping distortions in the output signal. Limiters are also used to give a track a finishing touch in the mastering, like making it louder, gluing everything together and balancing volume peaks out.


http://loudmax.blogspot.de/ (very good and low cpu limiter will keep your master out save)
http://lvcaudio.com/plugins/limited-z/ (best free mastering limiter in my opinion)
http://www.yohng.com/software/w1limit.html (this is also a great mastering limiter)
https://vladgsound.wordpress.com/plugins/limiter6/ (crazy analog limiter emulation, gives analog hardware coloring)

Here a short video of LoudMax cutting the peaks of a drum loop to make it louder, ignore after 0:50 where the guy opens another instance:
<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" data-src="https://www.youtube.com/embed/Dq868H1xMUs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

###  DAW

If you are looking for a way to edit notes/clips/tracks in a timeline style like classic digital audio workstations allow you to do, then you should definitely have a look at Temper. It is a full daw which can be loaded as a VST plugin. Only drawback, its 32-bin only:

http://www.angryredplanet.com/temper/download.html
![Temper](https://vvvv.org/sites/default/files/imagecache/large/images/http://www.angryredplanet.com/temper/media/ui-00.png) 

If you want to go meta, try this: Minihost modular is a modular VST plugin environment which has an integrated piano roll editor and free routing.

http://www.image-line.com/documents/news.php?entry_id=1398231311&title=minihost-modular-beta-3
<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" data-src="https://www.youtube.com/embed/hhfO9yYNlJY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

