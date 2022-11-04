---
uid: "contribution/demolition-media-hap-player"
uid-meta: "contribution/demolition-media-hap-player-meta"
comments: 
 items: 
  - uid: "241668"
  - uid: "241694"
  - uid: "241726"
  - uid: "241933"
  - uid: "248600"
  - uid: "248878"
  - uid: "260579"
  - uid: "275204"
  - uid: "275212"
  - uid: "280115"
  - uid: "280138"
  - uid: "280159"
  - uid: "280161"
uid-files: "contribution/demolition-media-hap-player-files"
title: "Demolition Media Hap Player"
image: "Screenshot (5).png"
contribution: "true"
---

##  Features
* Hardware accelerated (Nvidia/ATI/Intel graphics cards)
* Hap formats: Hap, Hap Q, Hap Alpha, Hap Q Alpha, **(new) Hap R**
* Containers: mov (preferred), avi
* No external codecs installation needed
* DirectX 11 video texture output
* Plays videos with alpha transparency
* **Reverse playback**
* Fully spreadable and dynamic
* **Async open/close (almost not affecting mainloop if number of videos is not insane)**
* 4k@120fps, 8k@60fps, 12k@60fps (limit is only your PC capabilities)
* VAudio-enabled (**multichannel sound supported**)
* 64-bit and 32-bit

##  License 
Free for non-commercial use.
**License needed for commercial use.**
Companies: 200€ per project per machine
Individual: 100€ per project per machine
Discount for multiple licenses applies 
[Purchase via e-mail](mailto:lev.panov@gmail.com)

##  Requirements: 
1. vvvv >= 45beta35.8
1. dx11 pack >= 1.3.1
1. VAudio pack for audio output (currently built against v18)

##  Installation
Unzip and copy "packs" folder to your vvvv root folder

##  How to encode videos
To play videos you would need to re-encode them to Hap first
[Encoding tips (pdf)](https://www.dropbox.com/s/u2wiccg9ru1tx41/Hap%20Encoding%20Tips.pdf?dl=1) [Additional](https://gist.github.com/dlublin/e4585b872dd136ae88b2aa51a6a89aac)

**Hap encoder for Adobe CC:** [github](https://github.com/disguise-one/hap-encoder-adobe-cc)

**(NEW) A faster/better quality commercial Hap encoder available now: [Jokyo Hap Encoder](https://jokyohapencoder.com)**

##  VL support
https://www.nuget.org/packages/VL.HapPlayer (same licensing as in beta)


##  FAQ
* Q: How to achieve the maximum performance out of the player?
* A: Try encoding without 2nd stage compression. You can save CPU time with that, at the cost of higher data-rate (it also depends on the content) -- your SSD should be fast! Add "-compressor none" to the FFmpeg arguments. I've managed to play 10k@50fps with this approach on my laptop.
* Q: I want to drive the playback with the frame index/LFO/external clock/sync playback on several machines
* A: There is such plugin version (non-public - for commercial projects only). Contact [e-mail](mailto:lev.panov@gmail.com)
* Q: What about reverse playback
* A: Yes!
* Q: I've exported the video from After Effects with audio track. It isn't being played nicely by hap player
* A: The audio from AE is heavy. Please re-encode with FFmpeg using the "-vcodec copy" option (will only process the audio stream, leaving video frames as is). It will be played fine then.
* Q: I have a Windows 7 machine, and all the hap player nodes are red.
* A: You're in a bad situation. Try 64-bit plugin version, or upgrade to a newer Windows version (8.1 is enough)


##  Changelog
2022-02-08
1. Fixed a very rare crash related to native textures usage
2. Other fixes and improvements 
3. (internal) Upgraged the native plugin build toolset from v140 to v142
4. Removed the deprecated modular nodes  

2020-10-13
1. Video texture uploading is being done in background now, making the mainloop decoupled and generally smooth even when playing a lot of videos
2. Reduced number of memory copying operations, gaining up to 10% of playback performance
3. Improved calculation of decode threads number for chunked Hap files
4. Hap R (high-quality BC7 texture compression) support

2020-03-14
1. Reverse playback
1. Smooth looping. No hiccups at the start of new loop — whether you have the start/end frames set or not!
1. Better playback speed control
1. Multi-channel audio support
1. Async open/close (almost not affecting mainloop if number of videos is not insane)
1. Improved stability and performance in some cases
1. Slightly less modular design. All the old nodes are still there, but now have “Deprecated” suffix in their names. You need to update them from the node browser in order for the old patches to work. New suggested nodes are HapPlayer/HapPlayerState. Async open works only there. HapAudio remains alive
1. Extra output pins with some useful info
1. (NEW) **A better frame-precise playback control is available now for commercial projects (contact via [e-mail](mailto:lev.panov@gmail.com))**


###  2017-06-20
1. Experimental support of non-multiple of 2 video resolutions
1. Accurate computation of the current frame index
1. The image queue size was increased to 10 frames/100Mb, which gives slightly better performance in some cases
1. Don't seek to the start when the playback is finished
1. Loop pin of HapAudioClock now accepts a boolean (on/off)
1. Fix Opened/Playing outputs of HapState: don't reset to false when opening a single video from the input Path spread
1. HapReaderNode: make number of ouput slices equal to maximum slicecount of (Path, Open) input spreads
1. You can open one video multiple times, or open a video using arbitrary Open slice, without opening all the slices prior to it in the Open spread
1. Now works with vvvv 45beta34.2