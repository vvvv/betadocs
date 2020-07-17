---
uid: d69020a3-d624-43ec-8ad0-d0dc72632fcd
---

# RMS

#### Related nodes
<span class="node">RMS (DShow9)</span>  
<span class="node">RMS (Bass)</span>  
<span class="node">Gist (VAudio)</span>  


The Gist (VAudio) tracks several features of the incoming audio:   
* RMS  
* PeakEnergy  
* ZeroCrossingRate  
* SpectralCentroid  
* SpectralCrest  
* SpectralFlatness  
* EnergyDifference  
* SpectralDifference  
* SpectralDifferenceHWR  
* HighFrequencyContent  
* PitchYin  

There are <span class="node">RMS (DShow9)</span> and <span class="node">RMS (Bass)</span> simple envelope followers. They return the current volume for the left and the right channel.  

#### Note

With all DShow9 pins (of type audio / midi / video) you can connect **each output to only one input** pin. Therefore it is not possible with the DShow9 system to play a file and analyse it at the same time. The BASS and VAudio doesn't have this restriction.  

Examples in your vvvv\girlpower\ directory:  
* Audio  



# FFT

#### Related nodes
<span class="node">FFT (DShow9)</span>  
<span class="node">FFT (VAudio Sink)</span>
<span class="node">FFT (BASS)</span>  
<span class="node">FFT (Bass NRT)</span>  
<span class="node">FFT (DShow9 4Channels)</span>  



There are several nodes performing a Fast Fourier transform:  
* <span class="node">FFT (DShow9)</span>, <span class="node">FFT (Bass)</span>, <span class="node">FFT (VAudio Sink)</span> return current volumes for a spread of frequencies  
* <span class="node">FFT (Bass NRT)</span> processes files without playing them (Non-RealTime version)  
* <span class="node">FFT (DShow9 4Channels)</span> returns four volumes on Bass, LoMid, HighMid and High frequency bands.  

An FFT returns a spread of amplitudes of a linearly distributed scale of frequencies. But based on experiments on human hearing perception it is known that the scale of frequencies is approximately logarithmic at the high-frequency end, and nearly linear at the low-frequency end.  

That means that human meatbags can very good distinguish between low frequencies but the high frequencies sounds almost all the same. Music producers of course make use of that fact, see <a href="http://en.wikipedia.org/wiki/Psychoacoustics" class="extURL" target="_blank">Psychoacoustics</a>.  

That’s not all. Amplitudes should be scaled in a way, that higher frequencies have a bigger scaling factor. Despite the fact that low frequencies carry high energies (resulting in big values coming from FFT), humans perceive low frequencies dull. That is why mid and high frequencies have to be scaled up (nonlinearly).  

The FFT Nodes have the <span class="pin">Frequency Scaling</span> exactly for that.  

For more info on perception check: <a href="http://en.wikipedia.org/wiki/Equal-loudness_contour" class="extURL" target="_blank">Equal-loudness contour</a>.  

Examples in your vvvv\girlpower\ directory:  
* Audio  



# Beat trackers

#### Related nodes
<span class="node">BeatDetector (Value)</span>  
<span class="node">BeatDetector (BASS)</span>  
<span class="node">BeatScanner (Bass)</span>  



There are some useful modules to track beats:  
* <span class="node">BeatDetector (Value)</span> / <span class="node">BeatDetector (Bass)</span> are looking for beats in a stream.  
* <span class="node">BeatScanner (Bass)</span> performs beat detection on a file.  

Examples in your vvvv\girlpower\ directory:  
* Audio  

