---
uid: f829d8c6-d8cd-45b9-bb96-6cb0b78345e2
---

# MIDI


<a href="http://en.wikipedia.org/wiki/MIDI" class="extURL" target="_blank">MIDI protocol</a>  
<a href="http://www.midi.org/about-midi/table1.shtml" class="extURL" target="_blank">MIDI specification</a>  
<a href="http://www.midiox.com/" class="extURL" target="_blank">Very helpful MIDI Utility</a>  
<a href="http://www.nerds.de/en/loopbe1.html" class="extURL" target="_blank">MIDI Virtual Driver</a>  
<a href="http://www.tobias-erichsen.de/" class="extURL" target="_blank">Multi MIDI Virtual Driver</a>  
<a href="http://www.copperlan.org/index.php/download" class="extURL" target="_blank">MIDI Virtual Network Driver</a>  

#### Related nodes
<span class="node">MidiNote (Devices)</span>  
<span class="node">MidiController (Devices)</span>  
<span class="node">MidiProgram (Devices)</span>  
<span class="node">MidiBend (Devices)</span>  
<span class="node">MidiClock (Devices)</span>  
<span class="node">TodoMap (TodoMap)</span>  
MidiIn (VAudio)  
MidiNode (VAudio)  
MidiFilePlayer (VAudio)  
...and many more  


In MIDI slang controllers are: volume knob, modulation wheel, pan fader, pedal, etc. The instrument as a whole is called a device and sends its data on a specified channel number.   

vvvv counts midi channels from 0 to 15 and notes from 0 to 127. Note's velocities and control values are defined in the range (0..1).  

The <span class="pin">Buffer Length</span> of the Midi input nodes sets the maximum number of incoming midi-messages that get queued for output in the patch. Only one message per vvvv-frame will be returned in the patch while within a frame's timespan more than one message could arrive.  

- If you want fast responses (messing around with a faderbox cause a lot of control messages): set the 'Buffer Length' low, even 0.  

- If you want to make sure that you receive every single midi-message: set the 'Buffer Length' to a high value (ie. 999).  

A handy patch to receive and understand what your midi device is sending:  
* IO\Midi\02_KnowYourDevice.v4p  

An example on how to receive different notes and control values on different channels:  
* IO\Midi\03_ReceivingNoteAndControl.v4p  

Check all other examples about Midi:  
* IO\Midi\  

### VAudio
VAudio Pack supports MIDI events. This has a big advantage because the midi events happen as the occur and do not get quantized by the vvvv mainloop.  
**<a href="https://vvvv.org/contribution/vvvv.audio-pack-alpha" class="extURL contribution" target="_blank">VAudio Pack</a> is contributed by <span class="user"><a href="https://vvvv.org/users/tonfilm" class="extURL" target="_blank">tonfilm</a></span>.**  


### TodoMap
There is also a useful MIDI & OSC mapper for vvvv called TodoMap. Check the video-tutorials from <a href="https://vvvv.org/contribution/launchpad-(todomap-launchpad)-todomap-tutorials" class="extURL contribution" target="_blank">this contribution</a> by <span class="user"><a href="https://vvvv.org/users/vux" class="extURL" target="_blank">vux</a></span> & <span class="user"><a href="https://vvvv.org/users/antokhio" class="extURL" target="_blank">antokhio</a></span>.  

**The TodoMap nodes are contributed by <span class="user"><a href="https://vvvv.org/users/vux" class="extURL" target="_blank">vux</a></span> and are coming with the <a href="https://vvvv.org/downloads#addonpack" class="extURL" target="_blank">addonpack</a>.**  


**Useful MIDI-Modules:**  
* <a href="https://vvvv.org/contributions/all/3075" class="extURL" target="_blank">Midi-related contributions</a>  
* [A range of Midi modules](TODO INTERNALLINK:kalle.Modules.MIDI) by <span class="user"><a href="https://vvvv.org/users/kalle" class="extURL" target="_blank">kalle</a></span>  

**Virtual Midi Ports use:**  
keep in mind that some virtual midi ports like loopBe or loopMidi need   
the same architecture at both ends 32 OR 64 bits.  
if you need to communicate between x86 and x64 softwares have a look at copperlan.  




