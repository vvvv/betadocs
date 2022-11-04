---
uid: "contribution/obsolete-see-addonpack-filestream-(ex9.texture-vlc)"
uid-meta: "contribution/obsolete-see-addonpack-filestream-(ex9.texture-vlc)-meta"
comments: 
 items: 
  - uid: "58090"
  - uid: "58095"
  - uid: "58096"
  - uid: "58097"
  - uid: "58101"
  - uid: "58102"
  - uid: "58104"
  - uid: "58120"
  - uid: "58121"
  - uid: "58179"
  - uid: "58200"
  - uid: "58628"
  - uid: "58687"
  - uid: "58754"
  - uid: "58825"
  - uid: "58838"
  - uid: "58839"
  - uid: "58898"
  - uid: "59162"
  - uid: "59190"
  - uid: "59502"
  - uid: "60590"
  - uid: "60645"
  - uid: "60742"
  - uid: "60772"
  - uid: "60804"
  - uid: "60813"
  - uid: "61100"
  - uid: "61154"
  - uid: "61218"
  - uid: "61247"
  - uid: "61299"
  - uid: "61304"
  - uid: "62154"
  - uid: "62215"
  - uid: "63008"
  - uid: "63910"
  - uid: "65456"
  - uid: "65477"
  - uid: "65708"
  - uid: "65810"
  - uid: "65974"
  - uid: "66013"
  - uid: "66603"
  - uid: "66609"
  - uid: "67109"
  - uid: "67997"
  - uid: "68231"
  - uid: "68243"
  - uid: "68251"
  - uid: "68309"
  - uid: "68355"
  - uid: "69337"
  - uid: "70266"
  - uid: "70608"
  - uid: "70626"
  - uid: "70662"
  - uid: "70841"
  - uid: "71243"
  - uid: "71247"
  - uid: "71295"
  - uid: "71626"
  - uid: "71658"
  - uid: "73231"
  - uid: "73232"
  - uid: "73241"
  - uid: "73320"
  - uid: "73321"
  - uid: "73350"
  - uid: "73368"
  - uid: "74830"
  - uid: "74842"
  - uid: "74892"
  - uid: "74997"
  - uid: "75070"
  - uid: "75074"
  - uid: "75094"
  - uid: "75716"
  - uid: "75723"
  - uid: "75727"
  - uid: "75729"
  - uid: "75740"
  - uid: "75755"
  - uid: "75766"
  - uid: "75769"
  - uid: "76025"
  - uid: "76058"
  - uid: "76077"
  - uid: "76078"
  - uid: "76113"
  - uid: "76114"
  - uid: "76125"
  - uid: "76177"
  - uid: "76185"
  - uid: "76186"
  - uid: "76459"
  - uid: "76472"
  - uid: "76473"
  - uid: "76474"
  - uid: "76519"
  - uid: "76797"
  - uid: "76823"
  - uid: "78363"
  - uid: "78713"
  - uid: "78733"
  - uid: "78827"
  - uid: "78831"
  - uid: "79174"
  - uid: "79216"
  - uid: "79224"
  - uid: "79304"
  - uid: "79326"
  - uid: "81303"
  - uid: "81349"
  - uid: "81355"
  - uid: "81626"
  - uid: "81829"
  - uid: "82168"
  - uid: "82169"
  - uid: "82172"
  - uid: "82174"
  - uid: "82221"
  - uid: "82452"
  - uid: "82453"
  - uid: "83013"
  - uid: "83041"
  - uid: "83042"
  - uid: "83048"
  - uid: "83054"
  - uid: "83056"
  - uid: "86820"
  - uid: "86843"
  - uid: "86846"
  - uid: "87552"
  - uid: "87560"
  - uid: "87565"
  - uid: "88168"
  - uid: "88183"
  - uid: "88204"
  - uid: "88222"
  - uid: "88235"
  - uid: "88326"
  - uid: "88836"
  - uid: "89056"
  - uid: "90510"
  - uid: "91378"
  - uid: "91440"
  - uid: "91586"
  - uid: "91764"
  - uid: "93675"
  - uid: "93782"
  - uid: "93814"
  - uid: "93825"
  - uid: "94363"
  - uid: "100461"
  - uid: "100753"
  - uid: "101123"
uid-files: "contribution/obsolete-see-addonpack-filestream-(ex9.texture-vlc)-files"
title: "[OBSOLETE, see Addonpack] FileStream (EX9.Texture VLC)]"
image: "vlc.png"
contribution: "true"
---

<div class="box">
###  For versions of the plugin after march 2012
THERE ARE TWO WAYS TO MAKE THE PLUGIN WORK:
1. if VLC player 2.x is installed in c:\Program Files\VideoLAN\VLC or in c:\Program Files (x86)\VideoLAN\VLC the plugin should work out of the box, and it will use the dlls from there.
2. if VLC player is installed somewhere else, you can either:
* copy the following files from your "VLC 2.0.x player" installation folder (http://www.videolan.org/) to the same directory as the Vlc0_5.dll (which should be ./plugins/Vlc in this example): *libvlc.dll, libvlccore.dll, the full plugin directory*
* edit the *./plugins/Vlc/libvlc_searchpath.txt* file and add the path to your VLC installation folder

###  For versions of the plugin before march 2012
THIS PLUGIN WON'T WORK UNTIL YOU COPY SOME FILES !!!

In order for it to work, you need to copy some files 
from your "VLC player" installation folder (http://www.videolan.org/) 
to the same directory as the Vlc0_x.dll (should be ./plugins/Vlc or similar in the examples):
- libvlc.dll
- libvlccore.dll
- the full plugin directory

Any version 1.1.X of VLC player should work. As soon as VLC 1.2 is out, I will try to update...

**From version 0.5 on, you need LibVLC 1.2**</div>

####  CHANGE LOG:
2012/08/12
* Should work on beta28 with and without /dx9ex
* Added some simple (not very accurate) looping.
* No shared texture output yet (actually it does, but vvvv and as a conseuence vvvv's TextureInfo node doesn't know about it yet)
* Maybe some of you noticed that since LibVLC 2, some 'filters' (like deinterlace=1 or vout-filter=transform) don't work anymore. This has been removed from LibVLC, and at this time, there is no alternative yet, until someone rewrites parts of LibVLC to re-enable this.

2012/03/07
* Plugin tries to use VLC player's dll's if it's installed, no more copying necessary.

2012/02/19
* Fixed some of the issues introduced in the previous version.

2012/02/03
* Updated to LibVLC 1.2 ! Should work on beta27.

2011/12/19
* Should fix the issue where video wouldn't render to texture for DVB streams.

2011/08/13
* Should fix the issue where the audio keeps playing after closing a patch.

2011/03/13
* Going fullscreen works again.

2011/03/07
* I think I fixed the remaining deadlock.
* Added relative paths support
* The plugin can now also properly load images (with alpha channel). I use the file extension to decide whether it's an image (loaded using some .net functions), or whether it's a video/audio file (loaded using Vlc). So some image extensions might not work yet, please let me know which images won't work, so I can check if I forgot to add that file extension.
* Current frame updated every frame (but still not very useful).


####  ABOUT THE Vlc PLUGIN:
* Written by Frederik Tilkin in 2010-2012
* Please check out VLC's wiki pages to see how to use filters, and directshowsources etc. You can open any source in VLC player, and use the same MRL + options (tick 'show more options' in the 'Open Media' dialog), except you have to separate every argument by a | (replace the : by |)
* A useful starting point might be http://wiki.videolan.org/Documentation:Play_HowTo/Advanced_Use_of_VLC

####  WHAT'S THE DIFFERENCE BETWEEN THIS PLUGIN AND FILESTREAM/VIDEOTEXTURE:
1. The fact that vvvv's VideoTexture only renders the video on 1 device (if you have 1 renderer on your primary display and another one on your secondary display, for example the beamer). The Vlc plugin makes sure the video is displayed on the 2 devices.
1. The fact that switching between files using the Filestream node, causes a framerate drop in vvvv. Since the Vlc plugin (pre)loads, starts and stops video's in a separate thread, vvvv's framerate will hardly be affected by switching between different video-files.
1. Vlc allows you to resize the decoded video. If you want to display 10 video's at the same time, chances are the resolution these 10 video's are shown on screen is much lower than their native resolution. Using Vlc you can minimize the number of pixels that have to be transferred to the graphics card, without having to recode the video's.
1. you can add some useful effects to the video, like deinterlacing. Nothing is more ugly than interlaced video. (obsolete as of LibVLC 2.0, but maybe possible again one day)
1. it is possible to load image files (with alpha channel) as textures too, all using the same node. Also without slowing down vvvv while loading a new image as a texture. Same for plain audio files.
1. in future, I want to be able to nicely loop video's using a crossfade of a configurable number of frames.
1. You could open internet streams (for example <mms://95.211.98.3/TV-ShowTv>, allthough opening these takes a long time, so be patient; also streaming FROM VLC player into VVVV works), webcams, your DVB receiver, DVD's etc. Check out VLC's generated commands for example when opening your webcam. I have chosen to split the various commands by using the | (pipe) symbol. Which means you could open your webcam using a filename that looks like *dshow:// | dshow-vdev=name of your webcam | dshow-adev= | dshow-caching=200*
1. And finally, it is fully spreadable!

So if any of this is useful to you, you could use this plugin. Otherwise it doesn't matter, and you could keep using FileStream connected to VideoTexture.


####  USAGE HINTS:
Basic usage should be quite straightforward, but VLC has some nice features built-in, some of which can be used in the plugin as well.

A few examples:
* If you want to use a webcam you can use something like:
 dshow:// | dshow-vdev=name of your webcam | dshow-adev= | dshow-caching=200
* The loop pin is implemented in a stupid way, but VLC can help you here, just use this as the filename:
 video.avi | input-repeat=-1
* or if you don't want to loop the entire file, but only from 5.5 to 10 seconds, you can even use:
 video.avi | input-repeat=-1 | start-time=5.5 | stop-time=10.0
* if the video or image should be resized, use the <span class="pin">forced width</span> and/or <span class="pin">forced height</span> input pins. If it is set to 0, it will use the file's native resolution. If you set both pins, it will take your resolution, if you only set width for example and set height to 0, the height will be calculated from the forced width, using the file's native aspect ratio. Example: resizing a 800x600 image/video to 400x0 will result in a texture size of 400x300. (Of course these pins will influence the 'preloaded' files, not the files that were already loaded!)
* Want to play a DVB-T stream, use something like (use the frequency, bandwidth and channel numbers that are applicable in your region):
 dvb-t://frequency=506000000:bandwidth=8 | programs=4144

####  KNOWN ISSUES:
* NO SHARED TEXTURE OUTPUT yet for beta28 and up: TODO
* Since LibVLC 2, 'filters' (like deinterlace=1 or vout-filter=transform) don't work anymore: LibVLC issue, maybe they'll fix it some day...
* Vlc does not render the beginning of files. A known and frustrating VLC player issue, that I can't do anything about <http://trac.videolan.org/vlc/ticket/3152>.
* RELATIVE PATHS: FIXED
* SEEKING WHEN LOOP IS OFF doesn't work: FIXED
* OPENING PATCH WITH PLAY OFF => PLAY DOESN'T WORK: FIXED
* POSIITION is WRONG: TODO, frame number will be updated every frame in this version, but it keeps counting when the file is paused or has stopped playing, so it still sucks ;)
* UNSTABLE ON OPENING: KNOWN, still seems to happen sometimes.
* SOMETIMES FILES DON'T PLAY OR ONE SLICE STOPS WORKING: FIXED I think, unless you go crazy switching with webcam in etc. on multiple pins
* REPEATS THE FIRST FRAMES ON SWITCHING: I guess it depends on the file format and codec. I don't think all files have this problem.
* LOOP IN AND OUTS (feature request): FIXED (but not accurate) Ideally I would like to be able to do a 'crossfaded' loop, where you can tell how many frames should be crossfaded. 
* Audio keeps playing after deleting node or closing patch: FIXED
* DVB problem where video wouldn't play, or would play in a new window: FIXED


####  ABOUT THE LIBRARIES USED:
nVlc is a .net wrapper library for the libvlc video decoder library:

The following dll's belong to nVlc (http://www.codeproject.com/KB/audio-video/nVLC.aspx):
- Declarations.dll
- Implementation.dll
- LibVlcWrapper.dll
- NLog.dll

REMARK: I made 1 small change to the nVlc version of september 2010:

 * in LibVlcMethods.cs I changed
```
<DllImport("libvlc")>
public static extern int libvlc_media_get_tracks_info(IntPtr media, ref libvlc_media_track_info_t tracks);

```
to

```
<DllImport("libvlc")>
public static extern int libvlc_media_get_tracks_info(IntPtr media, out IntPtr tracks);
```
since the original function is libvlc_media_get_tracks_info(IntPtr media, libvlc_media_track_info_t** tracks);



