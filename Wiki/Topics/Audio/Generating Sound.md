---
uid: 331b48a6-6dee-4ae3-8808-bf720e9c89e5
---

# DShow9

#### Related nodes
<span class="node">SourceBuffer (DShow9)</span>  

The <span class="node">SourceBuffer (DShow9)</span> is able to write Spreads of values to a multichannel soundcard.  





# VAudio

#### Related nodes
Osc (VAudio Source)  
IFFT (VAudio Source)  
MultiSine (VAudio Source)  
WaveTable (VAudio Source)  
BufferRead (VAudio Source)  
Granulator (VAudio Source)  


* **Osc (VAudio Source)** is a high quality anti-aliased digital oscillator  
* **IFFT (VAudio Source)** is an inverse FFT that can synthesize a waveform from its spectrum  
* **MultiSine (VAudio Source)** generates many sine waves at once  
* **WaveTable (VAudio Source)** plays a waveform given as spread in the desired frequency  
* **BufferRead (VAudio Source)** reads audio from a live generated audio buffer  
* **Granulator (VAudio Source)** reads audio in grains from a wave file  

**<a href="https://vvvv.org/contribution/vvvv.audio-pack-alpha" class="extURL contribution" target="_blank">VAudio Pack</a> is contributed by <span class="user"><a href="https://vvvv.org/users/tonfilm" class="extURL" target="_blank">tonfilm</a></span>.**  

Examples:  
* \girlpower folder in the VVVV.Audio pack directory  





# VST Instruments

<a href="http://en.wikipedia.org/wiki/Virtual_Studio_Technology" class="extURL" target="_blank">Wikipedia on VST</a>  

**VAudio**  
The <a href="https://vvvv.org/contribution/vvvv.audio-pack-alpha" class="extURL contribution" target="_blank">VAudio pack</a> has a newer VST integration which also works with 64bit vvvv.  

**Legacy**  
See the [VST-guide](TODO INTERNALLINK:VST) about VST Instruments in vvvv.  

Examples:  
* \girlpower\Audio folder in your vvvv directory  
* \girlpower folder in the VVVV.Audio pack directory  





# Beeps

#### Related nodes
<span class="node">Beep (Windows)</span>  
<span class="node">MessageBeep (Windows)</span>  


These shy annoying beeps are useful for debugging. Sometimes.  

* <span class="node">Beep (Windows)</span> calls the windows-api function Beep.  
* <span class="node">MessageBeep (Windows)</span> calls the windows-api function MessageBeep.  

