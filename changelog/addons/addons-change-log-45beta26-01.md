---
uid: 1eb053ed-23ec-400c-8968-a43e758374e7
---

# addons change log 45beta26-01
released on 17 08 11  
## new
* Info (System ComPorts): retrieves installed ComPorts  
* RoundRect (EX9.Geometry 2d) : Round rectangle mesh with inner/outer radius options.  
* Decompose (Transform) : returns translate/scale and rotation (as quaternion).  
* GetContactDetails (Box2d Spreaded) : Same as GetContactDetails (Box2d), but bodies/shapes ids/instances as per spread of two).  
* HasContact (Box2d) : To check if two specific shapes/bodies are in contact.  
* CreateBody (Box2d Persist) : Bodies created trough this node are persisted in the output pin, to avoid use of GetBodyById,GetBodyByCustom.   
* Camera (EX9.Geometry Collada): Returns view and projection matrix of selected cameras.  
* DeCons (Spreads) : splits a spread along binsizes (reverse function to <span class="node">Cons (Spreads)</span> )  
* DeCons (String) : -"-  
* DeCons (Color) : -"-  
* DeCons (Enumerations) : -"-  
* DeCons (Transform) : -"-  
* Store (Spreads) : (aka EditSpread or BuildSpread) stores a spread and sets/removes/insert slices w/o loop  
* Store (String) : -"-  
* Store (Color) : -"-  
* Store (Enumerations) : -"-  
* Store (Transform) : -"-  

## changed 
* SendEmail (Network): Now has a "Enable SSL" option / Encoding Option / Attachment posibility /can enable html in message body / full spreadable / sends email async (no vvvv freeze).  
* Occurrence nodes got a bin size  
* Combine (File Path): now known as MakePath (String) tries to make a (absolute) senseful Path out of any input  
* Stack (Color/Value/String): now has a Default/Reset pin, to set to an initial state (with bin size). Also has a config pin to allow the full stack content as output.  
* Segment (EX9.Geometry) : now has a phase pin  


## fixed
* Flash (EX9) : Mousecoordinates are transformed correctly now with transformations with rotation  
* Select (String Advanced) : select pin bug fixed  
* Select (Color Advanced) :  select pin bug fixed  
* Select (Enumerations) :  select pin bug fixed  
* Select (Transform) :  select pin bug fixed  
* ChannelData (Bass) : Was not outputting full buffer  
* Switch (Transform Advanced) : Was outputting nil if one transform in was nil, regardless if it was used at all. Now only output nil if one nil pin is used.  
* Box2d : Bodies, Joints and Shapes now got a LiteTime Pin, to indicate how long they been created.   
* UpdateShape (Box2d) : Fixed but when shape was not refiltered then group index changes.  
* Segment (EX9.Geometry 2d): Added a phase pin, also resolution now defaults to 20.  
* Box2d : You can now set TTL (Time to live) in bodies. Allows you to set a delay before destruction.  
* RS232 (Devices Spreadable): didn't evaluate if outputs not connected.  
* Mesh (EX9.Geometry Collada): didn't call MarkPinChanged on mesh output pin leading to various problems in downstream nodes.  
* + (Value Spectral Advanced), * (Value Spectral Advanced), Bounds (Spectral Advanced): expected behavior on nil input  
* HitTests (all) : now rechecks for hit properly if object properties have changed.  