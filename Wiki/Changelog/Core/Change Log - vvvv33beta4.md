---
uid: 8dec9ad3-9c3c-4105-94fb-ed7bdd98f791
---

# Change Log - vvvv33beta4
released 30 04 03  

## nodes
* new: Delaunay (2d Triangle)  
* new: Triangle (DX8 Indexed)   
* new: Pot Node (similar to Tint but for values)  
* new: Stopwatch (Animation). see module: Metronom (Animation)  
* new: ShellExecute (Windows)  
* new: ClientSocket (Network) and ServerSocket (Network) may be used to implement various network protocols in subpatches  
* new: OSCEncoder (Network) encodes a string according to the OpenSoundControl protocol to be sent over the network (supports only TypeTags c, i and s for now. the decoder is still to come)  
* changed: Tracker  (Devcies AscensionFlockOfBirds) outputs readable rotation values  
* improved: Tracker  (Devcies AscensionFlockOfBirds) coordinate system changed, is now left handed directx like (Y goes up)  
* improved: Heading, Cartesian, Polar.. should be more compatible now  
* fixed: Resample (Spreads): borderright bug, linear interpolation last slice bug  
* improved: Resample (Spreads): cylcic modes added  
* improved: Resample (Spreads): resample has much more interpolation modes now (hermite, cosine, ..)  
* Filters (LinearFilter, DeNiro, Newton, Oscillator, Damper): more stable; new: "Acceleration Out" added.  
* added: outputs for AccessedDate and CreatedDate to ModificationDate (Windows)   
* fixed (again): Perspective, Ortho..: Near Plane / Far Plane  
* new: Vertigo (Transform) allows to keep a plane at certain distance in focus means changing the field of view (FOV) will dolly the camera position accordingly so that objects at a certain distance keep their size.  
* new: MovingTriad (Transform) which allows to align an animated object on its path. see girlpowerpatch RollerCoaster.  
* new: vector pins introduced; use Vector (Join), Vector (Split) to build vectors.  
* several nodes are now available in Version "Vector"  
* new: LookAt (Transform) see girlpowerpatch RollerCoasterLookAt  
* new: Parallelepiped (Transform) see girlpowerpatch RollerCoaster  
* new: vector versions of several nodes  
* Attention: transform 2d, transform 3d work with center other than before; see: Rectangle (DX8 Regpoint)  
## modules
* new: Rectangle (DX8 Regpoint)  
* new: Metronom (Animation)  
* new: Swap (Spreads)  
* new: TestCamera (VVVV)  
* new: modules NetSend (Network Value), NetReceive (Network Value), NetSend (Network String), NetReceive (Network String)  
* new: rightclick a subpatch or renderer to toggle between componentmodes Window and Hidden  
* new: all patches that have a category in brackets (=modules) that are in vvvv_33betaX/modules (or any subdirectory) are now included in nodelists  
* changed: Camera (Transform Softimage) easier  
 
## general
* fixed: Flashing primitives bug when changing priority   
* improved: links to IOBox (Node) more stable  
* improved: patchclasses are now saved via their absolut path. all open patches with the same path are now really the same  
* improved: the mousewheel now works in pulldowns.  

## GDI
* improved: Matrix Viewport Transformation added. (try to view GDI with camera) Viewport ranges (-1,-1)..(1,1) from now on