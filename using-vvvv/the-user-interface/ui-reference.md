---
uid: 4612f4aa-0a2a-4f1a-bcfb-55c4bc0cb78c
---

## Main Menu
### Window
   |   |   
--- | --- | ---  
Snapshot    |<span class="keyseq"><kbd>Ctrl</kbd><kbd>1</kbd></span> 	|Takes a screenshot of the active window (including the cursor). If the window was a patch a .jpg with the name of the patch<br> and a successive number is placed in the directory the patch lays. Else you’ll be prompted to choose a filename to save.  
Snapshot Client 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>2</kbd></span> 	|Same as above but takes the screenshot without window border.  
...   |<span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>1</kbd></span> | same as <span class="keyseq"><kbd>Ctrl</kbd><kbd>1</kbd></span> but you are prompted to choose a filename to save.  
...   |<span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>2</kbd></span> | same as <span class="keyseq"><kbd>Ctrl</kbd><kbd>2</kbd></span> but you are prompted to choose a filename to save.  
Snapshot to Wiki        |<span class="keyseq"><kbd>Ctrl</kbd><kbd>3</kbd></span>  |opens [Kommunikator](xref:1765bb2b-f698-405a-b207-a995995fb52b) that allows you to preview, crop and upload images to vvvv.org. if you provide your login you can even add images to the pool of site-headers  
Windowed		|<span class="keyseq"><kbd>Alt</kbd><kbd>1</kbd></span> 	|See section about Subpatching  
In a Box |<span class="keyseq"><kbd>Alt</kbd><kbd>2</kbd></span> 	|See section about Subpatching  
Hide 	|<span class="keyseq"><kbd>Alt</kbd><kbd>3</kbd></span> 	|Close the current window, but leave the patch running. See section about Subpatching  
FullScreen 	|<span class="keyseq"><kbd>Alt</kbd><kbd>Enter</kbd></span> 	|Switch current Window to full screen. See section about Subpatching  
Save All 	|<span class="keyseq"><kbd>Alt</kbd><kbd>S</kbd></span> 	|Saves all unsaved patches  
Always on top       |<span class="keyseq"><kbd>Ctrl</kbd><kbd>T</kbd></span>  |Set the active window allways on top  
Close 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>W</kbd></span> 	|Close the current window and delete its node representation from the patch  
Close All 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>W</kbd></span> 	|Close all windows and open a default root patch. See section about Subpatching  


### Main
   |   |   
--- | --- | ---  
New Patch |<span class="keyseq"><kbd>Ctrl</kbd><kbd>P</kbd></span>, <span class="keyseq"><kbd>Ctrl</kbd><kbd>N</kbd></span> | Opens a new patch window in the root  
New Inspektor 	|<span class="keyseq"><kbd>CTRL</kbd><kbd>I</kbd></span> 	|Opens a new Inspektor window. this is assumed to be the *most important* Shortcut.  
Finder |<span class="keyseq"><kbd>Ctrl</kbd><kbd>F</kbd></span> 	|Opens [Finder](xref:869d5933-4693-4b32-a7f3-5b7cfcc3a07f) offering a search into your patches  
ProjectExplorer    |<span class="keyseq"><kbd>Ctrl</kbd><kbd>J</kbd></span> 	|Opens [Project Explorer](xref:721e9e4b-dec5-4786-878e-3efc4f09c5e7) (especially useful for adding .NET libraries to your Dynamic Plugins).  
Help 	|<span class="keyseq"><kbd>F1</kbd></span> 	|Opens the help patch for the selected node. If no node is selected a generic help patch is opened  
Online Help 	|<span class="keyseq"><kbd>Alt</kbd><kbd>F1</kbd></span> |Brings up the corresponding post from the ‘online node reference’ (vvvv.org/reference.php) <br>for the selected node in your default browser  
Fanclub 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>F1</kbd></span> 	|Opens the IRC online help patch  
About 		|<span class="keyseq"><kbd>Alt</kbd><kbd>A</kbd></span> |Shows credits and info about the computer  
ASCII Table |<span class="keyseq"><kbd>Alt</kbd><kbd>T</kbd></span> |Shows an ASCII table  
Show Root 	|<span class="keyseq"><kbd>Alt</kbd><kbd>R</kbd></span> 	|Shows the root patch of vvvv. See section about Subpatching  
Minimize 	|	|Minimizes vvvv to the taskbar  
Quit 	|<span class="keyseq"><kbd>Alt</kbd><kbd>F4</kbd></span> 	|Exits vvvv  


### Patch
   |   |   
--- | --- | ---  
Open 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>O</kbd></span>, <span class="keyseq"><kbd>Ctrl</kbd><kbd>Q</kbd></span> 	|Opens an existing patch in the root  
Save Patch 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>S</kbd></span> 	|Save patch  
Save Patch as.. 	|<span class="keyseq"><kbd>Shift</kbd><kbd>Ctrl</kbd><kbd>S</kbd></span> 	|Save current patch under a different name  
Lock 	|<span class="keyseq"><kbd>CTRL</kbd><kbd>E</kbd></span> 	|Disables all patching functionality. Only IOBoxes are enabled. Use this for performances etc. where you don’t want to accidentally change your patch. See [Hide on Lock](xref:10b82e0c-720a-48e1-91e4-d8c65d2c3be1#hiding-vs-closing-a-patch).  
Open in Explorer |<span class="keyseq"><kbd>Alt</kbd><kbd>E</kbd></span>|Shows the selected node/patch in explorer  
Open in Texteditor |<span class="keyseq"><kbd>Alt</kbd><kbd>Shift</kbd><kbd>E</kbd></span>|Opens the selected node/patch in the default text editor  
Revert to saved 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>R</kbd></span> 	|Closes the active patch unsaved and loads the last version from disk  


### Edit
   |   |   
--- | --- | ---  
Undo 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>Z</kbd></span> 	|Undo the last step. The Undo-history can be of arbitrary length  <br>Configure the behaviour with the <span class="node">Undo (VVVV)</span> node.  
Redo 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>Z</kbd></span> 	|Do the last undone step again.  
Cut 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>X</kbd></span> 	|Copy and delete selected nodes  
Copy 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>C</kbd></span> 	|Copy selected nodes  
Paste 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>V</kbd></span> 	|Insert copied nodes  
Paste modified values 	| 	|Apply the copied values to the selected node  
Duplicate 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>D</kbd></span> 	|Copy and Paste selected nodes  
Duplicate nodes and links 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>D</kbd></span> 	|Copy and Paste selected nodes and respective links  
Align 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>L</kbd></span> 	|Align the currently selected group of nodes either horizontally or vertically, depending on their existing orientation  
Select All 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>A</kbd></span> 	|Selects all nodes in the active patch  
Deselect 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>A</kbd></span> 	|Deselects all nodes in the active patch  
Boygroup 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>B</kbd></span> 	|Toggle Boygroup status of a node. See Boygrouping section  
[Hide on Lock](xref:10b82e0c-720a-48e1-91e4-d8c65d2c3be1#hiding-vs-closing-a-patch) 	|<span class="keyseq"><kbd>CTRL</kbd><kbd>H</kbd></span> 	|Nodes and connections can be marked, so that they are not drawn, when the patch is locked.  
Debug Mode 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>F9</kbd></span> 	|Toggles global Debug Mode on/off  
Debug Mode 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>F9</kbd></span> 	|Toggles Debug Mode of selected Nodes on/off  
Debug Mode 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>F10</kbd></span> 	|Visualizes spreadcounts  
Expose IObox 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>K</kbd></span> 	|Exposes selected IOBox for being controlled from the outside  
Alter Linktype 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>Y</kbd></span> 	|Cycle through several line styles for drawing links: straight, segmented, or Bezier.  
Make Relative 	|<span class="keyseq"><kbd>Alt</kbd><kbd>Shift</kbd><kbd>P</kbd></span> 	|Tries to find a relative path for the selected sub patch nodes  


## Additional Shortcuts
   |   |   
--- | --- | ---  
Snapshot Patch as .emf  |<span class="keyseq"><kbd>Ctrl</kbd><kbd>4</kbd></span> 	|Saves a .emf file of the whole patchwindow (all IOBoxes only display IO)  
Open 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>O</kbd></span>, <span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>Q</kbd></span> 	|Opens an existing patch in the active patch  
New Patch 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>P</kbd></span>, <span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>N</kbd></span> 	|Opens a new patch window in the active patch  
Group 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>G</kbd></span> 	|Creates a Subpatch from selected nodes   
Jump to parent  |<span class="keyseq"><kbd>Ctrl</kbd> + <kbd>the key below ESCAPE</kbd></span>	|Jumps to parent patch  
Toggle Windows 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>Tab</kbd></span> 	|Lets you switch through vvvv's windows (similar to MS Windows Alt-Tab)  
Lighten Patch 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>7</kbd></span> 	|Lightens the active patch’s background ***in versions >Beta8.3***  
Darken Patch 	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>6</kbd></span> 	|Darkens the active patch’s background ***in versions >Beta8.3***  
Toggle Window Frame	|<span class="keyseq"><kbd>Ctrl</kbd><kbd>8</kbd></span> 	|Toggles the frame of the active window on/off  
Zoom In  	|<span class="keyseq"><kbd>Ctrl</kbd></span><span class="keyseq"><kbd>+</kbd></span> 	|Enlarges the active patch ***Careful: BUGGY***  
Zoom Out 	|<span class="keyseq"><kbd>Ctrl</kbd></span><span class="keyseq"><kbd>-</kbd></span> 	|Scales the active patch down ***Careful: BUGGY***  

## and more Shortcuts
   |   |   
--- | --- | ---  
Scroll Patch 	|**Right click+Drag** in patch |to move the patch inside the window  
Create IOBox with values | start link from inputpin and end with **middleclick** | Creates IOBox containing values of connected Inputpin  
AutoName IOBox |**Middleclick** on linked IOBox | copies Pinnames of connected Nodes into Descriptive Name of IOBox  
AutoCreate send node| start link from output pin and end with <span class="keyseq"><kbd>CTRL</kbd></span>+Middleclick | Creates Send node with the 'Send String' set to the name of the output pin  
Reset Node    | <span class="keyseq"><kbd>ALT</kbd></span>+Rightclick on Node 	| Resets Node, resets all Pins to default value  
Reset Pin    | <span class="keyseq"><kbd>ALT</kbd></span>+Rightclick on InputPin | Resets Pin to default value  
Scroll Vertical    | <span class="keyseq"><kbd>Mousewheel</kbd></span> 	| scrolls up/down  
Scroll Vertical Fast   | <span class="keyseq"><kbd>CTRL</kbd></span>-Mousewheel 	|    
Scroll Horizontal    | <span class="keyseq"><kbd>ALT</kbd></span>-Mousewheel 	| scrolls left/right  
Scroll Horizontal Fast   | <span class="keyseq"><kbd>CTRL</kbd><kbd>ALT</kbd></span>-Mousewheel 	|    
move selected nodes by 1 px| <span class="keyseq"><kbd>CursorKeys</kbd></span> | moves nodes  
move selected nodes by 10 px| <span class="keyseq"><kbd>SHIFT</kbd><kbd>CursorKeys</kbd></span>| moves nodes faster...


## Code Editor
see [codeeditor shortcuts](xref:117e3ffc-1547-4470-8c49-f966d99bc031)  