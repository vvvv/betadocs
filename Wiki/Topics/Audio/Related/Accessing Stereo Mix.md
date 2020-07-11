---
uid: dbe5c817-bf69-4bdf-83bf-39d673772523
---

# Accessing Stereo Mix
You want to get sound that you're playing back on your PC into vvvv via <span class="node">AudioIn (Devices)</span>. Simply select the *Stereo Mix* (sometimes called *Rec. Playback* or similar) option on its <span class="pin">Driver</span>. If there is no such option try the following to make the option available in vvvv:  

## Windows Vista/7/8
* Make sure you have installed correct drivers for your sound card. After having done so restart vvvv and see if the option is now available, if not:  
* Check the Recording settings under: Control Panel > Sound > Recording Tab. Try to right click on empty space and check if Disabled / Disconnected Devices are visible. There you may see disabled devices. Rightclick and enable them, then restart vvvv to see if the option is now available.  

![Sound Recording Settings](~/img/SoundRecordingSettings.png "Sound Recording Settings")  

>note:  
If there are still no other devices than a Microphone under Recording Tab, then the only way to get a sound back from the sound card is to grab a cable and physically connect line-out and line-in (if you have one) on your machine.  

If this doesn't work for you as well you'll need a different soundcard to get this going. You can still play audio files though with <span class="node">FileStream (DShow9)</span>, <span class="node">FileStream (Bass)</span>, <span class="node">WavePlayer (DShow9)</span> and the likes.  
  

## Windows XP
Create a <span class="node">AudioRecordSelector (System)</span> node.   
* If it is red: you don't seem to have a soundcard or no driver installed for it.  
* If it is not red: check the <span class="pin">Device</span> to see if there are some devices available, choose 'Stereo Mix'.  

Here is how it looks like:  
![AudioRecordSelector](~/img/AudioIn-test-screen.jpg "AudioRecordSelector") 