---
uid: b27d2408-4af0-4384-ba30-a6faecb81e5f
---

# DShow9 effects

#### Related nodes
<span class="node">Distortion (DShow9)</span>  
<span class="node">ParametricEQ (DShow9)</span>  
<span class="node">Reverb (DShow9 Waves)</span>  
<span class="node">Reverb (DShow9 I3DL2)</span>  
<span class="node">Reverb (DShow9 Preset)</span>  


Only a small list of cheesy sound effects can be found in the DShow9 category.  

Examples in your vvvv\girlpower\ directory:  
* Audio  



# BASS effects

#### Related nodes
<span class="node">APF (Bass)</span>  
<span class="node">LPF (Bass)</span>  
<span class="node">Echo (Bass)</span>  
<span class="node">Clone (Bass)</span>  
<span class="node">Mixer (Bass)</span>  
<span class="node">Chorus (Bass)</span>  
<span class="node">Reverb (Bass)</span>  
<span class="node">Winamp (Bass)</span>  
<span class="node">AutoWah (Bass)</span>  
<span class="node">Flanger (Bass)</span>  
<span class="node">IceCast (Bass)</span>  
<span class="node">Compressor (Bass)</span>  
<span class="node">Distorsion (Bass)</span>  


>note:  
The BASS library is free only for non-commercial use. Check their <a href="http://www.un4seen.com/bass.html" class="extURL" target="_blank">website</a> for more information about licensing.  
  

The BASS category has some more effects.  

Note the unusual way the effects are applied to the stream: instead of as you'd expect to chain effects between the FileStream and the Mixer nodes with BASS the filters all apply to the FileStream to which they are connected upstream!   

All effects are attached seemingly parallel to a stream. Only their <span class="pin">'Priority'</span> pin allows you to specify the order the effects are being applied.  

Examples in your vvvv\girlpower\ directory:  
* Audio  



# irrKlang effects

#### Related nodes
<span class="node">FileStream (Irrklang)</span>  


>note:  
The irrKlang library is free only for non-commercial use. Check their <a href="http://www.ambiera.com/irrklang/irrklang_pro.html" class="extURL" target="_blank">website</a> for more information about licensing.  
  

The <span class="node">FileStream (Irrklang)</span> has a decent list of built in effects:  
* Chorus  
* Compressor  
* Distortion  
* Echo  
* Flanger  
* Gargle  
* I3DL2 Reverb  
* EQ  
* Wave Reverb  

All these effects are **hidden pins by default**. To access them have a look at the node with the [Inspektor](TODO INTERNALLINK:the-gui#Herr-Inspektor). There you can enable individual effects and make the corresponding pins visible by left-clicking the leftmost, lightgray box in the Inspektor (next to the pins value).  



# VST Plugins


VST-Plugins are either audio-effects or instruments that can be used with vvvv.  

#### DShow9 streams
VST plugins have to be placed in the  lib\nodes\vst folder. After a restart of vvvv they will be available in the nodebrowser among the other nodes.  

See the [extensive VST-guide](TODO INTERNALLINK:VST) about VST Plugins in vvvv.  

#### VAudio
The <a href="https://vvvv.org/contribution/vvvv.audio-pack-alpha" class="extURL contribution" target="_blank">VVVV.Audio pack</a> has a newer VST integration which also works with 64bit vvvv. It is fully spreadable and has a comfortable vst parameter pin exposure workflow and saves the current vst setting with the vvvv patch.  

#### Bass streams
VST plugins can also be applied to a Bass stream via <span class="node">VST (Bass DSP)</span>.  

Examples in your vvvv\girlpower\ directory:  
* Audio  

