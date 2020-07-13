---
uid: 026ac8ca-9bcc-45e4-abf3-ac079a44065b
---

# Performance
This page collects information regarding potential optimization of your patches.   

# Detecting Performance Issues
In order to observe the performance of your patch you have two instruments:  
* Use <span class="node">Timing (Debug)</span> or <span class="node">PerfMeter (Debug)</span> to keep an eye on your framerate  
* Use the [Debug Mode](TODO INTERNALLINK:Debug Mode) to see how much CPU-time each of your nodes/subpatches needs  

# Resolving Performance Issues
* Learn how to [control evaluation](TODO INTERNALLINK:subpatches#evaluation) of subpatches  
* Hide (Alt+3) patches (not only [dock](TODO INTERNALLINK:the-user-interface-in-detail#docking) them) to reduce the impact of vvvvs GUI on your CPU  
* Nodes that don't have an input like 'Enable', 'Read', 'Write', ... will see if their input is changed every frame and if so re-perform their task. With large spreadcounts this 'check-for-changed' can be be quite CPU-intesive and often you as a patcher actually know when the change has happened. In those situations use a S+H node before the CPU-intensive operation and only sample its input when you know it has changed.  
* <span class="node">MainLoop (VVVV)</span> has <span class="pin">Increase Timinig Precision</span> which is on by default. While causing a smoother framerate in many cases it also causes higher CPU-needs in all cases. You'll have to find find out for your case if you want to change this setting. Here is a good read on the topic [ http://randomascii.wordpress.com/2013/07/08/windows-timer-resolution-megawatts-wasted|Windows Timer Resolution Megawatts wasted].  
* <span class="node">Boost (VVVV)</span> can increase vvvv´s thread priority. In rare cases this may allow you to get the last quantum of performance out of your CPU.   
* Make sure to always use the latest drivers for your graphics card  
* <a href="http://www.overclockersclub.com/guides/windows_xp_services.php" class="extURL" target="_blank">Remove unneeded windows services</a>  
