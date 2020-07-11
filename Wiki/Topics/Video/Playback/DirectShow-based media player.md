---
uid: fe20c5bb-6f12-4ab0-a617-3766cccd352c
---

# DirectShow-based media player


#### Related nodes
<span class="node">FileStream (DShow9)</span>  
<span class="node">FileStream (DShow9 Boygroup)</span>  

<span class="node">FileStream2 (DShow9)</span>  
<span class="node">FileStream2 (DShow9 Boygroup)</span>  

<span class="node">VideoTexture (EX9.Texture VMR9)</span>  



This native node and its variations plays back all different kinds of videos Windows Mediaplayer plays as well. If a specific DirectShow codec is installed on a system the <span class="node">FileStream (DShow9)</span> can playback files encoded with that codec.  

It can also handle <a href="https://en.wikipedia.org/wiki/AviSynth" class="extURL" target="_blank">AviSynth</a> scripts. The script mimics itself as an AVI file and allows joining and editing several videos. Check the [AVIJoiner](TODO INTERNALLINK:elektromeier-AVSAVIJoiner) from <span class="user"><a href="https://vvvv.org/users/elektromeier" class="extURL" target="_blank">elektromeier</a></span>.  

Try the **FileStream2 (DShow9)** for hickupfree file switching.  
The **FileStream (DShow9 Boygroup)**'s special power is to syncronize several players on the same or several machines (in a [Boygroup](TODO INTERNALLINK:boygrouping-basics) setup).  

Their <span class="pin">Filename</span> pin is not spreadable, therefore only one file can be played at a time.  

However it's possible to have several <span class="node">FileStream (DShow9)</span> connected to their own <span class="node">VideoTexture (EX9.Texture VMR9)</span> and [AudioOut (DShow9)](TODO INTERNALLINK:AudioOut (DShow9)) in the same patch in order to play several files in parallel. Beware though that those streams will not run in sync by default.  

#### Synchronization
Multiple players can by synchronized locally or in a network scenario, see [Video Synchronization](TODO INTERNALLINK:video-synchronization).  

#### Note

With all directshow pins (of type audio / midi / video) you can connect **each output to only one input** pin. Therefore it is not possible with the DShow9 system to play a file and analyse it at the same time using nodes like <span class="node">Contour (FreeFrame DShow9)</span> or <span class="node">Trautner (FreeFrame DShow9)</span>.   

Examples in your vvvv\girlpower\ directory:  
* Video  



