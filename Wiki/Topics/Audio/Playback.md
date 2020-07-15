---
uid: ebe5bc2b-8945-43e5-90fb-5b08c1040347
---

# Introduction

#### There are five ways for playing back audio files:

* [FileStream (DShow9)](xref:ebe5bc2b-8945-43e5-90fb-5b08c1040347#filestream-dshow9)  
* [WavePlayer (DShow9)](xref:ebe5bc2b-8945-43e5-90fb-5b08c1040347#waveplayer-dshow9)  
* [FileStream (VAudio)](xref:ebe5bc2b-8945-43e5-90fb-5b08c1040347#filestream-vaudio)  
* [FileStream (Bass)](xref:ebe5bc2b-8945-43e5-90fb-5b08c1040347#filestream-bass)  
* [FileStream (Irrklang)](xref:ebe5bc2b-8945-43e5-90fb-5b08c1040347#filestream-irrklang)  




# FileStream (DShow9)

#### Related nodes
<span class="node">FileStream (DShow9)</span>  
<span class="node">FileStream (DShow9 Boygroup)</span>  
<span class="node">FileStream2 (DShow9)</span>  
<span class="node">FileStream2 (DShow9 Boygroup)</span>  
<span class="node">AudioOut (DShow9)</span>  


This node and its variations plays back the following formats:  
* mp3  
* wav  
* wma  
* aif  
* mid.  

Try the **FileStream2 (DShow9)** for hickupfree file switching.  
The **FileStream (DShow9 Boygroup)**'s special power is to syncronize several players on the same or several machines (in a [Boygroup](xref:9d029794-1266-4e60-961f-33e6f95af7e6) setup).  

Their <span class="pin">Filename</span> pin is not spreadable, therefore only one file can be played at a time.  

However it's possible to have several <span class="node">FileStream (DShow9)</span> connected to their own <span class="node">AudioOut (DShow9)</span> in the same patch in order to play several files in parallel. Beware though that those streams will not run in sync by default.  

See the [Multichannel Output](xref:909206b2-99b1-40a4-b477-826b7fbfef9d) section for more about playing back multichannel audio files.  


#### Note

With all directshow pins (of type audio / midi / video) you can connect **each output to only one input** pin. Therefore it is not possible with the DShow9 system to play a file and analyse it at the same time using nodes like <span class="node">FFT (DShow9)</span> or <span class="node">RMS (DShow9)</span>. However some sound cards have an option to access the *'Stereo Mix*' of all sound that's being played on it. In that case it’s possible to listen to the sound via separate <span class="node">AudioIn (DShow9)</span> and <span class="node">AudioOut (DShow9)</span>.   

Please check [Accessing Stereo Mix](xref:dbe5c817-bf69-4bdf-83bf-39d673772523).  

Examples in your vvvv\girlpower\ directory:  
* Audio  




# WavePlayer (DShow9)

#### Related nodes
<span class="node">WavePlayer (DShow9)</span>  


It plays back only one format:  
* 16-bit, 44kHz (multichannel) wav files  

Its <span class="pin">Filename</span> is spreadable, so **any number** of audiostreams can be played in parallel. This feature can be misused for the seamless switching between the files. Just feed all the files you want to play to the <span class="pin">Filename</span> pin, spread the <span class="pin">Play</span> pin and turn on its corresponding slice.  

WavePlayer also has some special powers, like routing channels to several outputs and fading towards the end of a loop to prevent clicks.  

By default WavePlayer routes channels as defined in the wavefile (in the most simple case it’s just the left speaker). But a custom routing table can be defined. See its helppatch for details on that.  

Examples in your vvvv\girlpower\ directory:  
* Audio  





# FileStream (VAudio)

**Download:**  
<a href="https://vvvv.org/contribution/vvvv.audio-pack-alpha" class="extURL contribution" target="_blank">VAudio Pack</a>  

#### Related nodes
FileStream (VAudio)  
Granulator (VAudio)  
AudioOut (VAudio)  



FileStream (VAudio) plays media formats supported in <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/dd757927(v=vs.85).aspx" class="extURL" target="_blank">Media Foundation</a>. It is fully spreadable, deals correctly with multichannel audio files and also retains good audio quality when changing the playback speed:  

* .3g2, .3gp, .3gp2, .3gpp  
* .asf, .wma, .wmv  
* .aac, .adts  
* .avi  
* .mp3  
* .m4a, .m4v, .mov, .mp4  
* .sami, .smi  
* .wav  


**<a href="https://vvvv.org/contribution/vvvv.audio-pack-alpha" class="extURL contribution" target="_blank">VAudio Pack</a> is contributed by <span class="user"><a href="https://vvvv.org/users/tonfilm" class="extURL" target="_blank">tonfilm</a></span>.**  

Examples:  
* Check the \girlpower directory in the VVVV.Audio pack  
* <a href="https://vvvv.org/contribution/vvvv.audio-node15-workshop-patches" class="extURL contribution" target="_blank">VAudio NODE15 Workshop Patches</a>  





# FileStream (Bass)


<a href="http://www.un4seen.com/bass.html" class="extURL" target="_blank">The BASS website</a>  

#### Related nodes
<span class="node">FileStream (Bass)</span>  
<span class="node">AudioOut (Bass)</span>  



note:  
The BASS library is free only for non-commercial use. Check their <a href="http://www.un4seen.com/bass.html" class="extURL" target="_blank">website</a> for more information about licensing.  
  

**The BASS series of plugins is contributed by <span class="user"><a href="https://vvvv.org/users/vux" class="extURL" target="_blank">vux</a></span> and is coming with the <a href="https://vvvv.org/downloads#addonpack" class="extURL" target="_blank">addonpack</a>.**  

<span class="node">FileStream (Bass)</span> plays back the following formats:  
* mp3  
* wav  
* aif  
* ogg  

Its <span class="pin">Filename </span> pin is not spreadable, therefore only one file can be played back at a time.  

Other than with DShow9 there are no restrictions as of how many output pins can be linked to from an input. So the sound can be analyzed and mixed at the time of playing it back.  

Multiple audiostreams (from different <span class="node">FileStream (Bass)</span> nodes) can be mixed using a <span class="node">Mixer (Bass)</span> and there are some built-in effects available (open the nodebrowser and type 'bass dsp' to find them).  

Examples in your vvvv\girlpower\ directory:  
* Audio  





# FileStream (Irrklang)


<a href="http://www.ambiera.com/irrklang/" class="extURL" target="_blank">The irrKlang website</a>  

#### Related nodes
<span class="node">FileStream (Irrklang)</span>  



note:  
The irrKlang library is free only for non-commercial use. Check their <a href="http://www.ambiera.com/irrklang/irrklang_pro.html" class="extURL" target="_blank">website</a> for more information about licensing.  
  

**This node is contributed by <span class="user"><a href="https://vvvv.org/users/sanch" class="extURL" target="_blank">sanch</a></span>, <span class="user"><a href="https://vvvv.org/users/phlegma" class="extURL" target="_blank">phlegma</a></span> and <span class="user"><a href="https://vvvv.org/users/readme" class="extURL" target="_blank">readme</a></span> and is coming with the <a href="https://vvvv.org/downloads#addonpack" class="extURL" target="_blank">addonpack</a>.**  

As stated in the <a href="http://www.ambiera.com/irrklang/features.html" class="extURL" target="_blank">irrKlang documentation</a> it plays back the following formats:  
* RIFF WAVE (*.wav)  
* Ogg Vorbis (*.ogg)  
* Free Lossless Audio Codec (*.flac)  
* Amiga Modules (*.mod)  
* Impulse Tracker (*.it)  
* Scream Tracker 3 (*.s3d)  
* Fast Tracker 2 (*.xm)  

Its <span class="pin">Filename</span>, <span class="pin">Play</span>, <span class="pin">Volume</span> and many other pins are spreadable, so **any number** of audiostreams can be played in parallel. <span class="node">FileStream (Irrklang)</span> is able to position and move sounds in 3d space and has a decent list of effects built-in right into the node (check Inspektor for enabling them).  

Examples in your vvvv\girlpower\ directory:  
* Audio  

