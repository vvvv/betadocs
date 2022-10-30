---
uid: "contribution/slotmanager"
uid-meta: "contribution/slotmanager-meta"
uid-files: "contribution/slotmanager-files"
title: "SlotManager"
contribution: "true"
---

SlotManager is a node that solves problems caused by reordering, inserting or removing slices in a spread. It was created to work with the DX11 filestream VLC node but it might have other applications where changing spread order or removing slices causes performance issues. 

Another approach to this problem is in the AnimationSlots examples in Girlpower 

THE PROBLEM 

The DX11 Filestream node is spreadable. If you provide it with a spread of video files you would get a spread of videos as textures. 

If you have 20 objects on screen that need unique video textures this is ideal. But what if you want to remove the 3rd object in the spread? 
Easy enough - you should remove the 3rd slice and you get 19 slices in total.  
However this introduces a major performance issue. 

From your perspective the spread refers to the same files but minus one slice. 
From the data perspective of the VLC node in frame A it has a spread of 20 slices. In frame B the spread has 19 slices. The first two refer to the same files as last frame and don't need to be reloaded. All the remaining slices appear to refer to changed files that must be reloaded (even though it's just the old names shifted down a slice, on a per slice basis they appear to have changed). 

This means you've got one less video to play the filestream node reloads 17 video files which can be a major performance bottleneck. 

THE SOLUTION 
Slot manager creates a spread with a fixed number of slots. An unoccupied slot will be filled with a default value. 
You input your spread of filenames. Inititally slot manager will fill the slots from the input sequentially.. 
Every time the input spread changes Slot Manager determines what has changed and removes old items, adds new items to blank slots and if blank slots aren't filled outputs the default value. 

You can use the 'Pre Reindex' pin to sort other incoming parameters that go with the filename (like transforms or play state) to stay in order. 

You can use the 'Post Reindex' pin to sort the textures or other parameters downstream of the filestream node so that they match the supplied input spread order.  

I recommend making the default value refer to a small but valid video file. Filestream seems to perform better being switched to a valid file rather than an invalid input. 
If you use postsorting you will never see this default file (blank texture) on and object. 

DRAWBACKS 
It relies on filenames being unique to sort them consistently into slots. If you have an architecture where you might reuse the same video file on several objects then instead feed SlotManager a unique ID string that you generate at object creation instead of the filename. Then use the Pre-ReIndex output to get slices of your filenames and feed that to filestream. 

By setting a fixed number of slots that means you always have that many instances of Filestream running. However if your system can't handle this then it probably won't handle it when you actually have 20 unique videos to run. 

Because it does string comparison it should be a reasonably good solution for around 100 objects but it wouldn't be efficient for say thousands of particles. You might get better performance with shorter key strings

REQUIREMENTS 
Uses VL, developed on vvvv50Beta35.8. 
DX11 pack and VLC needed for helppatch

INSTALL 
Unzip so the vl folder is above your patches folder. Or merge into your existing vl folder if you have one. 

USAGE 
See the helpatch

LICENCE
Free to modify for any use
Test Media is from the electric sheep project see  http://electricsheep.org
Test media licence https://creativecommons.org/licenses/by-nc/3.0/us/

Developed by Toby K while working at DotDotDot, Milan 
www.tobyk.com.au 
dotdotdot.it