---
uid: 3d0e7863-48f9-4bf9-bd83-c3ecc1f29ca8
---

# VST
>note:  
This is a pretty old vst integration.  
A newer one which also works with 64 bit vvvv is here:  
<a href="https://vvvv.org/contribution/vvvv.audio-pack-alpha" class="extURL contribution" target="_blank">vvvv.audio-pack-alpha</a>  
  

# Introduction

<a href="http://en.wikipedia.org/wiki/Virtual_Studio_Technology" class="extURL" target="_blank">VST-Plugins</a> (Virtual Studio Technology) are either audio-effects or instruments that can be used with vvvvs modest directshow/audio capabilities.   

VVVV is not shipping with any vst-plugin. See below for a listing of some free effects or get any other and put the files (or a directory that contains .dll plus possibly associated files such as soundbanks etc.) into   
 \lib\nodes\vst
Start vvvv and the plugin should now be available among the VST category in the nodebrowser. There is no generic vst-node, every vst-node is a wrapper for a specific vst-plugin and is named after it. Click on the plugin in the list and a node is created, which has an associated window showing the GUI of the plugin. This window can be closed/opened as usual by pressing Alt+1 or Alt+3.  

Per default the plugin shows two input pins and one output pin. The input pin must be connected to an audiosource-node (Waveplayer/Sourcebuffer/Filestream) or another vst-plugin (but still with an audiosource-node at the beginning of the chain). Vst-instruments must have an audio-input too. As vst-instruments overwrite the audiostream completely, it has no use to chain a vst-plugin before the vst-instrument. Vst-effects can be chained arbitrarily.  
 
Plugins typically have a large list of parameters, so they are all hidden by default and you have to activate them individually via the Inspektor. Clicking twice on the button left to the value of the parameter makes the pin show up on the node. In most cases these parameters are associated with a knob, slider or toggle on the GUI. If the value of the pin is changed, it can be seen and vice versa. If an Input-Node is connected to the vst-parameter-pin it dominates over the GUI. All parameter-pins range from 0 to 1 in vvvv and are mapped to the parameters range inside the plugin.  

Most Effects have two input-channels (stereo), but there are some, which have more. This property can be seen in the Inspektor as *Channel In Count* and *Channel Out Count*. You may have to prepare the source-node to the vst-plugin by changing its amount of channels accordingly (see the helpfile of the sourcebuffer or waveplayer).  

## Controlling VST plugins with MIDI
Vst-Instruments can receive midi-notes and transform them into sound. Midi-Notes can be provided either directly from input-data created in vvvv or the MidiNote-Node can be used to receive the midi-notes coming from an external device such as a midi-keyboard. There are more midi-msgs which can be sent to the plugin, have a look inside the inspector.  
 
Latency when controlling VST plugins with midi is an issue which is mainly due to vvvvs internal framerate not being really suitable for audiooperation.  

If you want to see demopatches to this topic download polykeys, Synth1 VST, SupaPhaser (see list below) and put the demopatches and the plugins in the vst-folder.  

# Tutorial

Download the Synth1 VST-plugin and uzip it into  
 \lib\nodes\vst
Now open vvvv, doubleclick in the patch and select the Synth VST-Node from the nodebrowser. Open the inspektor and enable the Midi Notes, Midi Notes Velocity and Midi Notes Send pins.   

Connect the IOBox to the Midi Notes-Pin, the Toggle-Node to Midi Notes Velocity-Pin and the TogEdge-Node to the Midi Notes Send-Pin. Everytime you press the button in the IOBox, the midi-note 49 with the velocity of 1.0 is send.   

![](~/img/vsttutorial_synth1.2.jpg "")  

The next patch shows the use of the MidiNote-Node to be able to receive midi-notes from external midi devices. Download the Polykeys-plugin, put it into   
 \lib\nodes\vst
and open vvvv. Select the Polykeys-Node from the nodebrowser, open the inspektor and enable the Midi Notes,Midi Notes Velocity and Midi Notes Send pins. Open the I-Node and MidiNote-Node. Put a IOBox with the value of 127 into the To-Pin of the I-Node. A spread ranging from 0..127 is now the output of the node, this corresponds to the 0..127 possible midi-notes. Connect the I-Nodes output to the Midi Notes-Pin of the Polykeys-Node and to the Note-Pin of the MidiNote-Node.   

Now put the Enable-Pin to 1 and select a midi-device in the Midi Input Port of the MidiNote-Node, then connect the Output-Pin to the Midi Notes Velocity-Pin of the Polykeys-Node and the On Data-Pin to the Midi Notes Send-Pin. The midi-notes of your device should now be send to the Polykeys-Synthesizer.  

![](~/img/vsttutorial_polykeys.2.jpg "")  

# VST Plugins tested to work with VVVV

**Nice free instruments**   

* <a href="http://www.geocities.jp/sam_kb/VOPM/" class="extURL" target="_blank">VOPM</a>  
* <a href="http://www.geocities.jp/daichi1969/softsynth/index.html#down" class="extURL" target="_blank">Synth1 VST</a> | [ Demopatch](TODO INTERNALLINK:/tiki-download_file.php?fileId=1731)  
* <a href="http://e-phonic.com/plugins/drumatic3.php" class="extURL" target="_blank">Drumatic 3</a>  
* <a href="http://aswave.altervista.org/vst.html" class="extURL" target="_blank">Polykeys</a> | [ Demopatch](TODO INTERNALLINK:/tiki-download_file.php?fileId=1729)  
* <a href="http://www.kvraudio.com/news/kotkas-sets-paax-3-pro-vsti-sampler-for-windows-free-19926" class="extURL" target="_blank">Paax</a>  
* <a href="http://glenstegner.com/softsynths.html" class="extURL" target="_blank">MiniMogueVA / Arp2600VA</a>  
* <a href="http://bicycle-for-slugs.org/" class="extURL" target="_blank">Oameal</a> | [Demopatch](TODO INTERNALLINK:/tiki-download_file.php?fileId=1732)  
* <a href="http://www.ugoaudio.com/" class="extURL" target="_blank">Texture1</a>  
* <a href="http://www.bostreammail.net/ers/iblit.html" class="extURL" target="_blank">iblit</a>  
* <a href="http://www.bostreammail.net/ers/polyiblit.html" class="extURL" target="_blank">polyblit</a>  
* <a href="http://www.amvst.com/index.php?name=Downloads&file=details&id=34" class="extURL" target="_blank">AnalogWarefare 3</a>  
* <a href="http://www.greenoak.com/crystal/download.html" class="extURL" target="_blank">Crystel</a>  
 
**Nice free effects**  

* <a href="http://illformed.org/blog/glitch/" class="extURL" target="_blank">Glitch</a>   
* <a href="http://www.audjoo.com/Helix.html" class="extURL" target="_blank">Audjoo Helix</a>  
* <a href="http://sourceforge.net/project/showfiles.php?group_id=133137" class="extURL" target="_blank">Buffer Synth</a>  
* <a href="http://ag-works.net/default.asp?page=plugins.ch2" class="extURL" target="_blank">Chorus</a>  
* <a href="http://bram.smartelectronix.com/plugins.php?id=1" class="extURL" target="_blank">SupaPhaser</a>  |[ Demopatch](TODO INTERNALLINK:/tiki-download_file.php?fileId=1730)  

If you find problems with any vst-plugin in vvvv please report them to <span class="user"><a href="https://vvvv.org/users/MEanimal" class="extURL" target="_blank">MEanimal</a></span>  

# Links
* <a href="http://en.wikipedia.org/wiki/Virtual_Studio_Technology" class="extURL" target="_blank">Wikipedia  about VST</a>  
* Start developing your own <a href="http://ygrabit.steinberg.de/~ygrabit/public_html/index.html" class="extURL" target="_blank">VST-plugins</a>.  
* <a href="http://www.hermannseib.com/vsthost.htm" class="extURL" target="_blank">VSTHost</a> is an amazing open source VST-Host.  
* <a href="http://www.kvraudio.com/" class="extURL" target="_blank">KVR Audio</a> is a huge database of vst-plugins and related stuff.   
* <a href="http://www.voxengo.com/group/freevst/" class="extURL" target="_blank">Voxengo</a> - free VST Plugins  
* The sourcecode (licence: LGPL) of <a href="https://vvvv.svn.sourceforge.net/svnroot/vvvv/directshowfilter/VS2005/DSVSTWrapper/trunk/" class="extURL" target="_blank">DSVSTWrapper.ax</a>: a directshow filter wrapping a VST host enabling the use of VST-plugins within any directshow graph.    
* <a href="http://www.voxengo.com/product/recorder/" class="extURL" target="_blank">Voxengo Recorder</a> is a VST plugin which allows you to record the output of the channel or bus into a stereo WAV file.Routing to MME (multimedia extensions) soundcard is also supported.  
* <a href="http://plasq.com/wormhole/" class="extURL" target="_blank">Wormhole</a> Wormhole2 is for audio professionals and musicians, allowing routing of audio between machines on a network.Wormhole2 is available for Mac VST + Audio Unit and Windows VST.   