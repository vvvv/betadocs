---
uid: c9e3b406-9c82-4f87-8656-ab9a910f30b4
---

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



