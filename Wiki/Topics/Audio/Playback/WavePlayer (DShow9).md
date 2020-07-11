---
uid: 2599751f-0a56-437e-90d9-366baf6b9ae8
---

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



