---
uid: b8c6dc51-bd3b-4161-9b65-6e2df279485f
---

# Change Log - vvvv33beta6.8
release 12 02 04  

## general:
* fixed: bug with VVVV crashing on CPUs with more than 3GHz and hyperthreading enabled.  
* fixed: bug with VVVV crashing on systems with strangely configured game devices.  
* fixed: JohnsonSequencer doesnt return -1 anymore when no keyframe was stored in the sequencer. now leaves the old value instead  
* fixed: pins of subpatches get sorted right away when moving inlets and outlets (ionodes of the subpatch)  
* new: pins can be removed from a node by clicking on the pinbutton in the inspector  
* new: deinterlacing of video is supposed to work for dv-interlaced video (may need to reconnect to VideoTexture or VideoOut after changing DeinterlaceMode Pin)  
* added: S (Node), R (Node) to establish abstract node connections  
* added: Map (Value, Interval): Maps the value in the given range to a proportional value in the given output range  
* added: Interval (Spreads): returns the index of the input interval in which the input lies  
* added: Differential (Spreads): calculates the differences between one slice and the next. The output spread has one slice less than the input  
* added: Integral (Spreads): Sums up a spread of values and output the partial sums. The output spread has one slice more than the input  
* fixed: bug in Delaunay (2d Triangle) when turning rebuild off  