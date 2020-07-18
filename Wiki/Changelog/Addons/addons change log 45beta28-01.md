---
uid: ad97d801-32e0-40fb-ae22-b885db701c11
---

# addons change log 45beta28-01
released on 14 08 12  

## Fixed Nodes
* Advanced Sequencer has new option to keep buffer position once we stop recording.  
* TodoMap current variable can be selected from main node (so learning can also be done through patch).  
* TodoMap gui updates when we switch learn mode.  
* SphericalSpreads spreaded had varying inital positions <a href="https://discourse.vvvv.org/t/sphericalspread-bug-with-spreaded-spreadcount" class="extURL forum" target="_blank">read></a>  
* Reader (File Advanced) index was not working when reading characterwise <a href="https://discourse.vvvv.org/t/reader-(advanced)-problem" class="extURL forum" target="_blank">read></a>  
* Map (Value Interval Advanced) bin size was inconsisten over pins and 0 caused freeze  
* TimerFlop Reset pin now spreadable <a href="https://discourse.vvvv.org/t/timerflop-reset-pin-not-spreadable-at-the-moment" class="extURL forum" target="_blank">read></a>  
* Bounds (Spectral Vector) was misbehaving on binsize 0 <a href="https://discourse.vvvv.org/t/bounds-(spectral-advanced)" class="extURL forum" target="_blank">read></a>  
* lots of fixes on various TextureFX modules  

## Changed Nodes
* TimerFlop: Time defaults to 1, new output Running indicating percentage until it switches the output to 1  
* Text EX9.Texture: adapted to new interface, should be faster when spreaded  
* DeCons now deprecated and (automatically) replaced by native Unzip node (Bin Versions)  
* Vector Size nodes( ... (... Advanced)) completely rewritten:  
  * changed Version postfix from Advanced to Vector  
  * Vector pin not hidden anylonger  
  * using IStream interface: a little slower on static input with low slice count, but much faster on higher slicecounts and changing input than before  
  * helper class is generic - resulted in some new nodes in other categories along the way  

## New Nodes
* TodoMap has node to delete a mapping on selected variable.  
* TodoMap node to retrieve mapping info on selected variable.  
* Typewriter (String)  
* CAR (... Bin)  
* CDR (... Bin)  
* Reverse (... Bin)  
* Shift (... Bin)  
* Mean, MeanSquare, RootMeanSquare, GeometricMean & HarmonicMean in Vector Versions  

* Bump, BlurRadial3D, Growth, Preview, RenderTargetFisheye, TransformTexture (details in helppatches)  
* CrossToCube, CubeToCross, CubeToPano and PanoToCube - modules for converting cubemap textures (check their helppatches to see why you need cubemaps)  
* many new TextureFX modules added by <span class="user"><a href="https://vvvv.org/users/lecloneur" class="extURL" target="_blank">lecloneur</a></span>  