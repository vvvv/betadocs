---
uid: 010a8c49-09d3-4226-be25-6d849e7f552a
---

# addons change log 45beta29-01
released on 24 12 12  

## new plugins
* Kinect Face tracker Node  

## fixed plugins
* Irrklang now plays samples by bang. Acts more than a sampleplayer than a Filestream  
* Irrklang now plays mp3 and flac files  
* Irrklang renamed to Filestream (Irrklang)   
* MinimumAreaRect (2d OpenCV) stops to spit lot of debug messages in TTY  
* FFT (Bass) was red if file was invalid  
* FFT and ChannelData (Bass) were throwing error on unload  
* Mixer (Bass) error fix on invalid file.  
* EyesWeb Nodes fix on empty string  
* Kinect Nodes Fixes to work on dx9ex  
* Kinect Nodes now use 1.6 version of the SDK  
* Eyeweb decoder had little bug on empty string.  

## fixed:
* FullscreenQuad (DX9) - blend modes fixed, and now using shader technique input instead of CreateEnum  

## new
* DepthToWorld (EX9.Texture Filter) - world space reconstruction from INTZ depth   
* TextureFX got a bunch of helppatches (along with various small bugfixes) - check the [list>](https://vvvv.org/sites/default/files/user-files/fxhelp.v4p)  