---
uid: 4612f4aa-0a2a-4f1a-bcfb-55c4bc0cb78c
---

## Main Menu
### Window
   |   |   
--- | --- | ---  
Snapshot    |<kbd>Ctrl 1</kbd> 	|Takes a screenshot of the active window (including the cursor). If the window was a patch a .jpg with the name of the patch<br> and a successive number is placed in the directory the patch lays. Else you’ll be prompted to choose a filename to save.  
Snapshot Client 	|<kbd>Ctrl 2</kbd> 	|Same as above but takes the screenshot without window border.  
...   |<kbd>Ctrl Shift 1</kbd> | same as <kbd>Ctrl 1</kbd> but you are prompted to choose a filename to save.  
...   |<kbd>Ctrl Shift 2</kbd> | same as <kbd>Ctrl 2</kbd> but you are prompted to choose a filename to save.  
Snapshot to Wiki        |<kbd>Ctrl 3</kbd>  |opens [Kommunikator](xref:1765bb2b-f698-405a-b207-a995995fb52b) that allows you to preview, crop and upload images to vvvv.org. if you provide your login you can even add images to the pool of site-headers  
Windowed		|<kbd>Alt 1</kbd> 	|See section about Subpatching  
In a Box |<kbd>Alt 2</kbd> 	|See section about Subpatching  
Hide 	|<kbd>Alt 3</kbd> 	|Close the current window, but leave the patch running. See section about Subpatching  
FullScreen 	|<kbd>Alt Enter</kbd> 	|Switch current Window to full screen. See section about Subpatching  
Save All 	|<kbd>Alt S</kbd> 	|Saves all unsaved patches  
Always on top       |<kbd>Ctrl T</kbd>  |Set the active window allways on top  
Close 	|<kbd>Ctrl W</kbd> 	|Close the current window and delete its node representation from the patch  
Close All 	|<kbd>Ctrl Shift W</kbd> 	|Close all windows and open a default root patch. See section about Subpatching  


### Main
   |   |   
--- | --- | ---  
New Patch |<kbd>Ctrl P</kbd>, <kbd>Ctrl N</kbd> | Opens a new patch window in the root  
New Inspektor 	|<kbd>CTRL I</kbd> 	|Opens a new Inspektor window. this is assumed to be the *most important* Shortcut.  
Finder |<kbd>Ctrl F</kbd> 	|Opens [Finder](xref:869d5933-4693-4b32-a7f3-5b7cfcc3a07f) offering a search into your patches  
ProjectExplorer    |<kbd>Ctrl J</kbd> 	|Opens [Project Explorer](xref:721e9e4b-dec5-4786-878e-3efc4f09c5e7) (especially useful for adding .NET libraries to your Dynamic Plugins).  
Help 	|<kbd>F1</kbd> 	|Opens the help patch for the selected node. If no node is selected a generic help patch is opened  
Online Help 	|<kbd>Alt F1</kbd> |Brings up the corresponding post from the ‘online node reference’ (vvvv.org/reference.php) <br>for the selected node in your default browser  
Fanclub 	|<kbd>Ctrl F1</kbd> 	|Opens the IRC online help patch  
About 		|<kbd>Alt A</kbd> |Shows credits and info about the computer  
ASCII Table |<kbd>Alt T</kbd> |Shows an ASCII table  
Show Root 	|<kbd>Alt R</kbd> 	|Shows the root patch of vvvv. See section about Subpatching  
Minimize 	|	|Minimizes vvvv to the taskbar  
Quit 	|<kbd>Alt F4</kbd> 	|Exits vvvv  


### Patch
   |   |   
--- | --- | ---  
Open 	|<kbd>Ctrl O</kbd>, <kbd>Ctrl Q</kbd> 	|Opens an existing patch in the root  
Save Patch 	|<kbd>Ctrl S</kbd> 	|Save patch  
Save Patch as.. 	|<kbd>Shift Ctrl S</kbd> 	|Save current patch under a different name  
Lock 	|<kbd>CTRL-E</kbd> 	|Disables all patching functionality. Only IOBoxes are enabled. Use this for performances etc. where you don’t want to accidentally change your patch. See [Hide on Lock](xref:10b82e0c-720a-48e1-91e4-d8c65d2c3be1#hiding-vs-closing-a-patch).  
Open in Explorer |<kbd>Alt E</kbd>|Shows the selected node/patch in explorer  
Open in Texteditor |<kbd>Alt Shift E</kbd>|Opens the selected node/patch in the default text editor  
Revert to saved 	|<kbd>Ctrl R</kbd> 	|Closes the active patch unsaved and loads the last version from disk  


### Edit
   |   |   
--- | --- | ---  
Undo 	|<kbd>Ctrl Z</kbd> 	|Undo the last step. The Undo-history can be of arbitrary length  <br>Configure the behaviour with the <span class="node">Undo (VVVV)</span> node.  
Redo 	|<kbd>Ctrl Shift Z</kbd> 	|Do the last undone step again.  
Cut 	|<kbd>Ctrl X</kbd> 	|Copy and delete selected nodes  
Copy 	|<kbd>Ctrl C</kbd> 	|Copy selected nodes  
Paste 	|<kbd>Ctrl V</kbd> 	|Insert copied nodes  
Paste modified values 	| 	|Apply the copied values to the selected node  
Duplicate 	|<kbd>Ctrl D</kbd> 	|Copy and Paste selected nodes  
Duplicate nodes and links 	|<kbd>Ctrl Shift D</kbd> 	|Copy and Paste selected nodes and respective links  
Align 	|<kbd>Ctrl L</kbd> 	|Align the currently selected group of nodes either horizontally or vertically, depending on their existing orientation  
Select All 	|<kbd>Ctrl A</kbd> 	|Selects all nodes in the active patch  
Deselect 	|<kbd>Ctrl Shift A</kbd> 	|Deselects all nodes in the active patch  
Boygroup 	|<kbd>Ctrl B</kbd> 	|Toggle Boygroup status of a node. See Boygrouping section  
[Hide on Lock](xref:10b82e0c-720a-48e1-91e4-d8c65d2c3be1#hiding-vs-closing-a-patch) 	|<kbd>CTRL H</kbd> 	|Nodes and connections can be marked, so that they are not drawn, when the patch is locked.  
Debug Mode 	|<kbd>Ctrl F9</kbd> 	|Toggles global Debug Mode on/off  
Debug Mode 	|<kbd>Ctrl Shift F9</kbd> 	|Toggles Debug Mode of selected Nodes on/off  
Debug Mode 	|<kbd>Ctrl F10</kbd> 	|Visualizes spreadcounts  
Expose IObox 	|<kbd>Ctrl K</kbd> 	|Exposes selected IOBox for being controlled from the outside  
Alter Linktype 	|<kbd>Ctrl Y</kbd> 	|Cycle through several line styles for drawing links: straight, segmented, or Bezier.  
Make Relative 	|<kbd>Alt Shift P</kbd> 	|Tries to find a relative path for the selected sub patch nodes  


## Additional Shortcuts
   |   |   
--- | --- | ---  
Snapshot Patch as .emf  |<kbd>Ctrl 4</kbd> 	|Saves a .emf file of the whole patchwindow (all IOBoxes only display IO)  
Open 	|<kbd>Ctrl Shift O</kbd>, <kbd>Ctrl Shift Q</kbd> 	|Opens an existing patch in the active patch  
New Patch 	|<kbd>Ctrl Shift P</kbd>, <kbd>Ctrl Shift N</kbd> 	|Opens a new patch window in the active patch  
Group 	|<kbd>Ctrl G</kbd> 	|Creates a Subpatch from selected nodes   
Jump to parent  |<kbd>Ctrl+ the key below ESCAPE</kbd>	|Jumps to parent patch  
Toggle Windows 	|<kbd>Ctrl Tab</kbd> 	|Lets you switch through vvvv's windows (similar to MS Windows Alt-Tab)  
Lighten Patch 	|<kbd>Ctrl 7</kbd> 	|Lightens the active patch’s background ***in versions >Beta8.3***  
Darken Patch 	|<kbd>Ctrl 6</kbd> 	|Darkens the active patch’s background ***in versions >Beta8.3***  
Toggle Window Frame	|<kbd>Ctrl 8</kbd> 	|Toggles the frame of the active window on/off  
Zoom In  	|<kbd>Ctrl</kbd><kbd>+</kbd> 	|Enlarges the active patch ***Careful: BUGGY***  
Zoom Out 	|<kbd>Ctrl</kbd><kbd>-</kbd> 	|Scales the active patch down ***Careful: BUGGY***  

## and more Shortcuts
   |   |   
--- | --- | ---  
Scroll Patch 	|**Right click+Drag** in patch |to move the patch inside the window  
Create IOBox with values | start link from inputpin and end with **middleclick** | Creates IOBox containing values of connected Inputpin  
AutoName IOBox |**Middleclick** on linked IOBox | copies Pinnames of connected Nodes into Descriptive Name of IOBox  
AutoCreate send node| start link from output pin and end with <kbd>CTRL</kbd>+Middleclick | Creates Send node with the 'Send String' set to the name of the output pin  
Reset Node    | <kbd>ALT</kbd>+Rightclick on Node 	| Resets Node, resets all Pins to default value  
Reset Pin    | <kbd>ALT</kbd>+Rightclick on InputPin | Resets Pin to default value  
Scroll Vertical    | <kbd>Mousewheel</kbd> 	| scrolls up/down  
Scroll Vertical Fast   | <kbd>CTRL</kbd>-Mousewheel 	|    
Scroll Horizontal    | <kbd>ALT</kbd>-Mousewheel 	| scrolls left/right  
Scroll Horizontal Fast   | <kbd>CTRL-ALT</kbd>-Mousewheel 	|    
move selected nodes by 1 px| <kbd>CursorKeys</kbd> | moves nodes  
move selected nodes by 10 px| <kbd>SHIFT+CursorKeys</kbd>| moves nodes faster...


## Code Editor
see [codeeditor shortcuts](xref:117e3ffc-1547-4470-8c49-f966d99bc031)  