---
uid: 76f3717c-5da9-4a2a-9d53-4c5b982291a6
---

# TimelinerSA - a multipurpose Timeline

![](~/img/timeliner_1.jpg "")  

This is a standalone, crossplatform, <a href="https://github.com/vvvv/vvvv-sdk/tree/develop/vvvv45/src/nodes/plugins/Animation/Timeliner" class="extURL" target="_blank">opensource</a> timeline application. It allows you to define keyframes of values, strings and colors over time and receive the values of a specific point in time via UDP/OSC.  

# Download
see: <a href="https://vvvv.org/contribution/TimelinerSA" class="extURL contribution" target="_blank">TimelinerSA</a>  

## Install & Run
* Simply extract all files to a nice directory.  

### Windows
Doubleclick TimelinerSA.exe. If it crashes or nothing happens at all you may not have <a href="http://www.microsoft.com/downloads/en/details.aspx?FamilyID=ab99342f-5d1a-413d-8319-81da479ab0d7" class="extURL" target="_blank">.net3.5 SP1</a> installed  

### Linux, OSX and Solaris
The .net equivalent for other platforms is <a href="http://www.mono-project.com/Downloads" class="extURL" target="_blank">Mono</a>. Tested on Ubuntu with mono2.4. To run simply call  
 mono TimelinerSA.exe 
from a commandline. That should be it.   

## Known Problems
* seems not to start on OSX, will have to investigate that still.   

**Please report all troubles/findings in the [forum](https://vvvv.org/forums).**  

# Manual
press any of the following buttons on the top to create a new:  
* +R: ruler pin  
* +V: value pin  
* +S: string pin  
* +C: color pin  
* +M: midi pin (windows only)  

## Pins
In the PinHeader to the left pins can be given a name. This name is used as the pinname within vvvv. Pressing the X-Button deletes the pin. Use dragdrop on the PinHeader to change the order of pins. ClickDragging UpDown in a small zone on the bottom of the PinHeader a pins height can be changed.  

## Slices
When hovering a slice with the mouse some buttons appear on the left. They allow you to delete a slice add a slice (above or below the current slice) and move them up or down.  

## Mouse 
Doubleclick within a pin to create a new keyframe. Right-Doubleclick a keyframe to delete it.  

Select a keyframe by clicking on it or select multiple keyframes by click-drag spanning a selection rectangle. Use CTRL and ALT keys to add/remove keyframes to a selection.  

Move keyframes by dragging them:   
* left mouse button: change time  
* middle button: change time and value  
* right button: change value  
Pressing SHIFT while dragging allows for finer changes. Pressing CTRL while dragging makes keyframes snap to automatas states and the timebar.  

Doubleclick a keyframe to open an editor and change its values. This also works when multiple keyframes are selected. Note that only values changed in the editor will be written to the keyframes. Therefore as long as you don't change the time all keyframes will stay at their time-position but only will be set to the same value.   

RightClick-drag in an empty area of a pin/track:  
* left-right to pan/move the timeline   
* up-down to zoom   

## Keyboard Shortcuts
* SPACE: toggle play/pause  
* BACKSPACE: stop and rewind  
* HOME: jump to first state (or 0 if automata not in use)  
* END: jump to last state  
* PageUp: jump to next state  
* PageDown: jump to last state  
* DELETE (ENTF): delete selected keyframes  
* CTRL  
  * while dragging a keyframe: snap to automata states  
  * L: time align selected keyframes  
  * A: select all keyframes  
  * A & SHIFT: select all keyframes of hoverin pin  
* SHIFT  
  * while dragging a keyframe: make smaller steps  
  * A: select all keyframes of hovering slice  

## Midi Pin
The Midi Pin is still quite experimental and will only work on windows. By clicking on the **.mid* in the PinHeader you can select a midi-file to be loaded. The individual midi-tracks as specified in the file will appear as Slices. Note that only tracks that have notes will show up.   

You can edit notes in time and pitch and delete them. Adding notes or changing velocity is not yet implemented.   

Pressing the [S] button next to the filename will save the file. Note: Simply loading and saving a file will alter your original midi-file! Not all information present in your original file may be saved in the new file.  

## Automata
Timerliner includes a simple finite state automata which lets you specify some logic that influences the course of time. Activate it via the checkbox labeled *A* for *Automata*.   

### States
Per default the automata includes the following 3 states:   
* -INF  
* loop  
* +INF  
that make up a simple loop. While you can get rid of or change the first two, the last one will always be there, as it sits at infinity and you'll hardly reach it.   

Doubleclick in an empty area to create a new state/keyframe or doubleclick an existing state/keyframe to modify it. DoubleRightClick a state to delete it.   

Note, that each state spans from the previous one to its own visual representation. The keyframes in the Automata area therefore always only specify the end of a state.  

Move states in time using the left mousebutton. Use the right mousebutton to scale all keyframes of this state and move all following keyframes further in time. Use the middle mousebutton to scale the keyframes of the next state and move all previous keyframes in time accordingly. Hard to explain, still indispensable.  

### Events
Every state can have any number of *events* that can cause a statechange at any time. Every state has one event for sure, the *OnEnd* event, which specifies the action to execute when the states end is reached.   

DoubleClick a state/keyframe to change its name, time and specify additional events. In the middle textbox in the upcomming editor you can specify a list of event/action pairs, separated via linebreaks, like:  
 OnBang next
 OnSupa pause
 OnBad play
For readability it is recommended to start events with *On...*  

### Actions
Every event needs an action which will be executed as soon as the event occurs. The following is a list of built-in casesensitive actions with their corresponding icons as seen on the keyframes:  
 next      >>
 previous  <<
 loop      ><
 play      >
 pause     ||

If you write any other string next to an event it will be treated as a state and on execution of the event the automata will jump to the beginning of that event or pause if an event with such a name is not present.  

## Multiple Tabs
By double-clicking in the empty space next to a tab you can open more instances of the timeline. Middle-click on a tab removes it.   

## OSC
### Receiving from TimelinerSA
All of Timeliners current values are being sent via UDP using the OSC protocoll. Specify a target IP address (127.0.0.1 is the localhost) and a port (default: 4444).   

All values are sent in one OSC-Bundle. The individual messages addresses comprise of the base-address set in the edit-field + the pinname. e.g.:  

 /timeliner/Value0
 /timeliner/String0
 /timeliner/Color0

### Sending to TimelinerSA

TimelinerSA can be controlled via OSC commands. It listenes to commands sent to the port set via the rightmost numberbox in the interface (which defaults to 5555).   

Send the commands to the base-address as set in the edit field + the command you like to controll. e.g.:  

* Play: takes 0 (pause) or 1 (play) as argument  
 /timeliner/Play 1
* Set Time: takes 0 (don't set time) or 1 (set time) as argument  
 /timeliner/Set Time 1
* Time In: takes a single floating point value to specify the current time  
 /timeliner/Time In 0.234

# Changelog
## upcoming
* added <span class="pin">Speed</span> to specify the playspeed  
* fixed snapping of keys to state (now again aligned to start of next frame)  
* changed interaction: leftdrag: change time, rightdrag: change value, middle drag: change both  
 
## beta10 25 02 11
* fixed: smoother scrolling/zooming via rightdrag leftright/updown  
* fixed: keyframes now can be selected after the splitter was moved  
* fixed: snap to state: now keeps all selected keyframes in correct relative distance  
* new: "follow" and "jump" auto-scrolling modes  
* new: snap to timebar  
* new: pins now ask for confirmation on being deleted  
* new: pin that returns names of all automatastates  
* new: add/remove keyframes to selection via ctrl/alt click  

## beta9 08 12 09
* fixed: dragging a state with middle/right mousebutton now also saves changes  
* now running in cleaner hoster  

## beta8.1 17 10 09
* fixed a bug that would pop when Automata was not enabled  

## beta8 10 10 09
* dragging a state with middle/right mousebutton scales below keyframes accordingly.   
* keyframes and timebar now snap to automata states when pressing CTRL while dragging  
* improved drawing of automata states  
* keyframe editors now also available in collapsed pins  
* fixed bugs reported [here](https://vvvv.org/tiki-view_forum_thread.php?forumId=20&comments_parentId=28660#threadId28709) and [here](https://vvvv.org/tiki-view_forum_thread.php?forumId=20&comments_parentId=28341#threadId28711)  

## beta7.1 19 09 09
* u7 found something was odd with the accompanying .dlls  

## beta7 19 09 09
* collapsed view is finally useful  
* time input can now take a spread of times that is distributed to the pins  
* pressing ALT while moving multiple selected keyframes moves each keyframe proportionally  
* keyframe editors now also available in collapsed view  

## beta6 - 09 01 09
* midi: now uses the first tempo change specified in a file, not the last.  
* translation is now saved/loaded correctly  
* viewer crashes on zoom/translate  

## beta5.2 - 30 11 08
* fixed loading of broken savegame.xml as reported [here](https://vvvv.org/tiki-download_file.php?fileId=1846)  
* collapsed value-pins now load correctly  
* no more toggling of PLAY/PAUSE when in text-edit field  

## beta5.1 - 05 11 08
* no more crashes on linux and OSX (using mono >=1.91)  
* now loads midi-files that have no tempo specified  
* no more error when changing tempo/rhythm with no midi-file loaded  

## beta5 - 28 09 08
* added Midi Pin (+M) (windows only)  
* current slice value is now being displayed again  
* renaming pins now holds its keyframes [as](https://vvvv.org/tiki-view_forum_thread.php?forumId=20&comments_parentId=20678#threadId22082) reported here]  

## beta4.3 - 17 09 08
* adding removing AutomataPin now adapts upper pinarea  
* values left/right of keyframes are now clamped (not falling back to 0)  
* pinorder now correctly shown in debugmode  
* mouse is now cyclic for zooming and panning  
* value keyframes are now clipped to min/max during dragging  
* keyframe info is no longer clipped to keyframes slice  
* color-keyframes now can be dragged with correct speed  
* color-keyframe hue adjustment is now cyclic  

## beta4.2 - 16 09 08
* no more OSC-crash with too many pins [as](https://vvvv.org/tiki-view_forum_thread.php?forumId=20&comments_parentId=21502) reported here] and [here](https://vvvv.org/tiki-view_forum_thread.php?comments_parentId=21503&topics_threshold=0&topics_offset=0&topics_sort_mode=lastPost_desc&topics_find=&forumId=20)  
* no more wrong default values [as](https://vvvv.org/tiki-view_forum_thread.php?comments_parentId=21503&topics_threshold=0&topics_offset=0&topics_sort_mode=lastPost_desc&topics_find=&forumId=20) reported here]  

## beta4.1 - 05 05 08
* no more crash on scrolling with wheel  
* no more crash with colorpins scrolled out of sight  
* no more wrong clipping with spreaded pins half scrolled out of sight  
* collapsed pins now clip correctly on splitpane  
* changing a keyframe now has priority to moving the timebar  

## beta4 - 02 05 08
* now saving all pinsettings in one pin (needs manual conversion of old savegame.xml)  
* now saving pincollapsed and allinone states  
* added PageUP, PageDOWN shortcuts  
* new output for Automata: spread of state-times  
* added splitpane: have static pins on top and scrolling pins below  
* use dragdrop on pinheaders to change their order  

## beta3.2 - 22 02 08
* right-click-drag-up/down to zoom  
* Home/End buttons to jump to first/last state  
* pins/slices better to distinguish visually  
* no more crash on deleting pins  
* keyframes can be selected more precisely  

## beta3.1 - 19 02 08
* fixed: Min/Max of ValuePin not initializing correctly  

## beta3 - 16 02 08
* added Automata for looping and more  
* improved ruler drawing  

## beta2 - 29 12 07
* should now open without crash on all pcs with .net installed  
* can now be triggered via OSC   

## beta1 - 24 12 07 - initial release

# Related Projects
For a listing of similar alternatives see ((Animation))