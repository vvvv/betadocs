---
uid: 2a13595d-5869-40d3-8ee5-19a11cb160e9
---

# Change Log - vvvv33beta8
released on 20 10 04  

## general
* NEW HOMEPAGE!! you're invited to change our wiki, post your patches and help us on illustrating what vvvv is about  
* Screenshot of the Moment: press Ctrl-3 to post your current vvvvindow ontop of the wiki. this works with any vvvv-window. (So make sure to have the renderer selected when you want to show us your results)  
* Open Dynamics Engine (ODE) added in a first experimental version  

## new nodes
* Attractor (Value)  + build attractors in n-dimensional rooms. this node is a generalization of the other more special Attractor Nodes  
* HWND (Windows) node which will return a spread containing all handles of windows with a given name  
* ShowWindow (Windows) node which allows to show, hide, minimize, normalize and maximize windows and bring them to the front.   
* SendMessage (Windows) experimental, untested and dangerous node to send any message to any window in the system.  
* Copier (File Async) will do asynchrounuous file copies. uses one thread which will copy all files after another. Progress out will go from 0 to 1, jumping back to zero if copy is done. Note that classic copier has a spreaded DoCopy pin, the async version has a single DoCopy pin.  
* AVIParser spits out textures and some more info for a spread of avi-files. rather slow but quite handy.  
* Bell (Devices TAPI) potentially rings the bell on any telephone in the world. Named after Alexander Graham Bell. Note that this node will only ring the bell it will neither talk to the other party or transmit data. the only additional feature is detection of liftoff at the other side. the connection pin will return the status. note that to detect connection status the node needs an voice-capable modem. you may be able to configure your "AVM ISDN Custom Config" virtual modem by setting the init-string to "ATS31=4" this will switch it to voice mode. other modems are not tested. warning: this node may dial arbitrary numbers with your modem.  
* DMX (Artnet)  new nodes allow the easy sending and receiving of DMX data over UDP via the Artnet protocol. So vvvv can communicate bidirectionally with professional lighting consoles and use Artnet Nodes as DMX inlets and outlets, all over standard ethernet cabling. note the subnet and universe pins in the inspector. the text entered as descriptive name in your node will be shown in your lighting desk. the node will fake a sender ip adress. while a hack, this allows the multiple independent receivers on the same physical ip adress shown in different lines in the lighting desk. see http://www.artisticlicence.com/dwnart.htm for details of the Artnet protocol  
* SysLog (VVVV) Node for remote debugging  the node will broadcast all log messages in the RFC3164 Syslog format ( see http://www.faqs.org/rfcs/rfc3164.html ) Just create the node and set the threshold accordingly. so anybody in the same subnet can pick the log info up and parse/store/analyze them at will. this may be helpful in fullscreen boygroup setups to check the status of the clients. as the syslog format is an open standard, there are many sophisticated syslog receivers readily available ( see for example http://www.kiwisyslog.com/software_downloads.htm )  
* BoundingBox (EX9.Geometry Mesh) returns axis aligned bounding boxes for the several subsets within a mesh  
* Grid (EX9.Geometry) creates a grid - mesh with given resolution + color, texture coordinates included  
* Info (EX9.Texture) returns info about texture: width, height, number of levels included, format  
* HSV (Color Split), HSV (Color Join) representing the Hue Saturation Value Color Model added have a look at girlpower\color no transform.v4p  

## fixes
* ShellExecute (Windows) now bugfixed in asynchronuous nonwindowed mode.    
* Queue (Spreads) up to 3 times faster.  
* RingBuffer (Spreads) spreadable.  
* Complement (Color) doesn't influence alpha  
* + (Color) outputs alpha values: alpha1 + alpha2  
* Sort (Spreads) sorts at dimensions faster  
* Substitute (String)  
* InsertSlice (Spreads)  
* + (String): had an issue with changing pincount  
* + (String Spectral): (now has a Bin Size instead of a Bin Count pin)  
* Complement (Color): no longer complements alpha  
* Radix (Value): had an issue..  
* comments have correct size now  
* SliceInspektor does not collapse so fast  
* IOBoxes show special character for empty sets  
* IOBox (Node) shows descriptive name  
* IOBox (String) accepts dropped files on individual slices  
* IOBox (Value) accepts non-subtype-conform values via keyboard  
* subpatches have an ugly icon if they are saved with their absolute path  
* no more dead ends when deleting a node while making a connection  
* when saving a patch vvvv tries to save all subpatches, effects, freeframes...with a relative name  
* Dialogs got accelerator keys  
* SaveDialog adapts its size to the length of a filename and has a better feeling   
* VVVV now starts without administrator rights  

## changed
* Help files are now searched for in the corresponding folder  
Note that you have to use the exact corresponding folder/subfolder structure.   
And that you do NOT move the files anymore because of relative paths in the helpfiles. Note that you strictly have to admitt the folder structures of downloaded modules  
examples:   
 \help\modules\enos\Within (Value) help.v4p
 \help\freeframe\dllname help.v4p
 \help\effects\effectname help.v4p
* in all cases when a pin expects positive integers in the valid range [0..aPositiveNumber[ then feeding in a negative value is interpreted as counting from backwards (-1 is wrapped around and means aPositiveNumber-1) examples of affected nodes: GetSlice.Index, SetSlice.Index (..), MidiController.Channel, RetroColor.Index (..), FlashRenderer.StartFrame (StopFrame defaults to last frame = -1)  
* rewrite of lowlevel boygroupstuff. now with enhanced smoothness.  
* Color Inspector is working with HSV Color mode from now on (use the Ctrl Modifier to increase Saturation)  
* HSL: HSB (Join, Split, Transform) renamed into HSL(Join, Split, Transform). Brightness renamed into Lightness.  
* AttractorSpread (Spreads) now has more meaningfull pins  
* Resample (Spreads) BinSize added  