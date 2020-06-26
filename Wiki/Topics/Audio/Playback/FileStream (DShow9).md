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
The **FileStream (DShow9 Boygroup)**'s special power is to syncronize several players on the same or several machines (in a [Boygroup](TODO INTERNALLINK:boygrouping-basics) setup).  

Their <span class="pin">Filename</span> pin is not spreadable, therefore only one file can be played at a time.  

However it's possible to have several <span class="node">FileStream (DShow9)</span> connected to their own [AudioOut (DShow9)](TODO INTERNALLINK:AudioOut (DShow9)) in the same patch in order to play several files in parallel. Beware though that those streams will not run in sync by default.  

See the [Multichannel Output](TODO INTERNALLINK:audio-output) section for more about playing back multichannel audio files.  


#### Note

With all directshow pins (of type audio / midi / video) you can connect **each output to only one input** pin. Therefore it is not possible with the DShow9 system to play a file and analyse it at the same time using nodes like <span class="node">FFT (DShow9)</span> or <span class="node">RMS (DShow9)</span>. However some sound cards have an option to access the *'Stereo Mix*' of all sound that's being played on it. In that case it’s possible to listen to the sound via separate <span class="node">AudioIn (DShow9)</span> and <span class="node">AudioOut (DShow9)</span>.   

Please check [Accessing Stereo Mix](TODO INTERNALLINK:Accessing Stereo Mix).  

Examples in your vvvv\girlpower\ directory:  
* Audio  


