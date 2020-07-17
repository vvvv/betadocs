---
uid: 909206b2-99b1-40a4-b477-826b7fbfef9d
---

# Output

#### Related nodes
<span class="node">AudioOut (DShow9)</span>  
<span class="node">AudioOut (VAudio)</span>  
<span class="node">AudioOut (BASS Asio)</span>  

<span class="node">FileStream (DShow9)</span>  
<span class="node">WavePlayer (DShow9)</span>  
<span class="node">FileStream (VAudio)</span>  
<span class="node">FileStream (BASS)</span>  


There are 2 different types of multichannel audio hardware:  

1. real multichannel hardware typically comes as external USB or FireWire devices and has 4/8/16 channels of input and output
1. cheabo built-in 5.1 or 7.1 surround sound cards coming on most modern mainboards.


**1. External MultiChannel Audio Hardware**  

These cards can be addressed in vvvv only using their WDM drivers which always only offer to use their channels in pairs of stereo. These pairs (like 'Channel 1-2', 'Channel 3-4', ...) are exposed via the <span class="pin">Driver</span> pin of the <span class="node">AudioOut (DShow9)</span>.  

Addressing the channels of such a hardware individually only works using ASIO drivers which are not supported by vvvv's native DShow9 nodes.  

The <a href="https://vvvv.org/contribution/vvvv.audio-pack-alpha" class="extURL contribution" target="_blank">VVVV.Audio.Pack</a> or the BASS plugins provided by <span class="user"><a href="https://vvvv.org/users/vux" class="extURL" target="_blank">vux</a></span> supports ASIO drivers.   

If you have the [addonpack](https://vvvv.org/downloads/) installed look out for a node called <span class="node">AudioOut (BASS Asio)</span> and check its helpfile for further instructions.  


**2. Built-in 5.1 or 7.1 Surround Sound Cards**  

Multiple channels of a built-in 5.1 or 7.1 surround card can be addressed using the <span class="node">FileStream (DShow9)</span> and <span class="node">WavePlayer (DShow9)</span>.  

Examples in your vvvv\girlpower\ directory:  
* Audio  

