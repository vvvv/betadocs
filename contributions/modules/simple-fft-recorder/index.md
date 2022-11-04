---
uid: "contribution/simple-fft-recorder"
uid-meta: "contribution/simple-fft-recorder-meta"
comments: 
 items: 
  - uid: "250965"
  - uid: "251001"
uid-files: "contribution/simple-fft-recorder-files"
title: "Simple FFT Recorder"
contribution: "true"
---

Since a while I was looking forward to find some time and improve this primitive but useful tool.
So I came back with a revised (and a much better version I would say) of this simplistic module which has two distinct parts, a Recorder and a Reader one.
The idea was to record in Real Time (remains as a drawback indeed) mp3 or wav files and saving them as txt files in order to play them again in sync with an NRT writer.
The general "endeavour" is working pretty well so if you are a patient guy or girl then please be my guest.

* You must always keep the same Framerate between <span class="node">Recorder</span> and <span class="node">Reader</span>
* If you are not using an <span class="node">writer(dx11 Texture 2d NRT Advance)</span> or any equivalent then you will absolutely need a <span class="node">MainLoop</span>, set the <span class="pin">TimeMode</span> to increment (*this goes for both patches if you are using them separately*) and you are done.
* Some times other applications(Ableton Live for instance) may affect the framecount, this is causing a difference between the recorded and the actual frames. The only known workaround is to shutdown the "HARMFUL" application :P 

enjoy

any feedback would be appreciated !

Thanks in advance ! 


[nissidis](http://vvvv.org/users/nissidis)