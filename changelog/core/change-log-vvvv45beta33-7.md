---
uid: c414f3fc-0836-4438-9258-86d604360623
---

# change log - vvvv45beta33.7
released on 21 01 15  

## general
* some DShow9 now correctly show as missing (red) in x64   
* setup x64 now has Directshow checkbox grayed out (since custom filters not working in x64 anyway)  
* subtle bug fix for boygrouping. when working on a boygroup setup it could happen that patches (that are not yet instantiated on the client) get corrupt while editing that same patch. The error surfaced when you first boygrouped that patch that hasn't been instanciated yet on the client.   
* fixed change flag issue on pins when having the inspector open.  
* ALT+T now pops up a fancy ASCII table  
* fixed nasty access violations when running a boygroup using UDP - see <a href="https://discourse.vvvv.org/t/boygroup-network-error-stops-listening-to-master" class="extURL forum" target="_blank">boygroup-network-error-stops-listening-to-master</a>  
* fix of subtle bugs that can occured when ui eveluated input pins. in some cases value changes of inputs got acknowledged by the ui - without notice from within the node that depends on the change info.  

## new nodes
* OneEuroFilter (Animation): Simple speed-based low-pass filter for noisy input in interactive systems  
* RGB / HSV (Color Join Picker) create colors from the a la Photoshop range of values (RGB: 0..255, H: 0..359°, S and Alpha: 0..100%)  
* PBKDF2 (Raw) generates a key using the PBKDF2 cryptography function.  
* Encrypt / Decrypt (Raw 3DES) perform Triple DES cryptography algorithm on raw streams.  
* Encode / Decode (String File) use file URI scheme for file paths.  
* AsTexture (Raw) interprets a sequence of bytes (of a pixmap) as a texture.  
* Ellipsis (String) clips the string to the given length and adds up ellipsis characters.  

## changed nodes
* CameraCone (EX9) replaces the CameraPreview (Transform DX9) from the addonpack - visualizes the cone of a Camera in the scene.  
* CameraPreview (EX9) replaces the SecondLook (EX9 Softimage) - visualizes the cone of a Camera in a separate Renderer.  
* AsRaw (EX9.Texture) in RAW mode now returns bytes in expected order.  
* DynamicTexture (EX9.Texture Raw) now has an <span class="pin">Apply</span>  
* UDP (Network Client) has a new (inspektoronly by default) <span class="pin">Local Port</span>  

## fixed nodes
* AviParser (EX9.Texture) now working again  
* Automata: IMPORTANT bug fix. Automata didn't register its evaluationCB on its outputs. This messes up whole patches, since the output data might be framedelayed depending on which node gets evaluated first. We added a legacy Automata to be able to not break patches, that need the old broken automata to work correctly. Please replace with new automata and adjust everything else if necessary.  
* fixed null pointer exception when using more than 16 slices in Changed (Raw) node.  
* fixed major performance drop in Changed (Raw), FrameDelay (Raw) and Queue (Raw) nodes.  
* fixed access violations in AsRaw (EX9.Texture) node.  
* IOBox (Raw) now shows getsliced slices correctly.  
* fixed network nodes (UDP/TCP) when dealing with large byte streams  
* fixed double reload issue of HTTP (Network Server) node - see <a href="https://discourse.vvvv.org/t/force-flush-http-(server))) and [forum:http-(network-server)-delivers-changed-content-at-2nd-refresh" class="extURL forum" target="_blank">force-flush-http-(server)](TODO INTERNALLINK:forum:http-(network-server)-delivers-changed-content-at-2nd-refresh" class="extURL forum" target="_blank">force-flush-http-(server)) and ((forum:http-(network-server)-delivers-changed-content-at-2nd-refresh</a>  
* fix for Decay (Animation) for when not evaluated each frame  

## plugin interface
* the slice count of plugin raw output wasn't initialized properly.  
* fixed read and write methods of Raw in- and output streams.  

## girlpower
* added \Animation\Animation Slots  
* added \Transformations\Drag   
* added \Graphics\DX9\Geometry\Dynamic Meshes 