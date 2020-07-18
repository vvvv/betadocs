---
uid: 33db0834-5f79-4463-a075-56c0e15daa8f
---

# Change Log - vvvv33beta7.4
released on 13 06 04  

## general
* if you experience problems opening patches saved with a version prior to beta7.4 you may want to read the following:   
* LEGACY MODULES - we renamed some nodes and pins and removed some nodes. nodes we removed have been replaced by a subpatch (placed in: \modules\legacy) that does the same thing as (+/-) the original node. those subpatches will be automatically inserted instead of the missing node.   
* RELATIVE PATH vs. MODULE - a problem may occur when your patches contain nodes with a relative filename that have the same name as one of your modules. until beta6.8 the rule was: if a patch is referenced relatively and cannot be found vvvv looked recursively in the /modules directory. there was no difference between a relative subpatch and a module. only relative patches have been prefered by vvvv. beta7.4 now distinguishes between modules and relative patches by marking them with a joker (mouseover a module to see the joker). same applies to freeframe and effects files.   
  * advantage: you can now open effects, freeframe and patch files relative, absolute (drag on patch or 'open in patch' via menu) or via their 'joker'-directories: vvvv/effects, vvvv/freeframe, vvvv/modules and be sure to get the same patch opened the next time.  
  * disadvantage: when loading an old patch its not obvious if a relative patchname is meant to be a module or not. so (only for old patches) vvvv looks for a relative patchname in the /modules directory. if its not there its treated like an ordinary relative subpatch.  note: if you happen to have a relative patch with the same name as a module the module will be preferred when loading with new versions. so for this conversion-step modules are preferred as opposed to beta6.8 where the relative patch was preferred.   
* EXCEPTIONS  -  some things can not be converted automatically:   
  * some nodes did an "internal TogEdge" in former versions: e.g. Toggle (Animation) only recognized the upedge of a signal and toggled once. now the behaviour is: as long as the Input is 1 the node toggles. now you can toggle in two frames after each other, which wasn't possible before (open ToggleAutomata.v4p in the girlpower to see what's possible now with a simple toggle). Even nodes which do performance critical tasks like Dir (File) now behave like that. as long the DoRescan pin is set to 1 the directory will be rescanned each frame. to prevent such behaviour use TogEdge (Animation).   
  * [TSFilterMode] and [TSAddressMode] are now [Filter] and [Address]. while this naming conversion will be done automatically you will have to reconnect their outputs. but now no longer to a texture, but directly to the renderobject (e.g Quad) showing the texture.   
  * same goes for texture transformations. they are no longer attached to the texture-node but directly to the renderobject, effect resp.   
  * if you feel like the automatic conversions don't work for you or you have other problems loading your old patches don't hesitate to bug us.  
* there is no more setup.exe - use uninstall to get rid of installed components  
* new debug mode: select nodes and press CTRL-SHIFT-ALT-F9 or just press CTRL-F9 to debug/profile your entire system. see which subpatches take most of your time  
* bangs should work better now. even on pins. just one click  
* shortcuts for takeing screenshots have changed. see mainmenu.   
* VideoInput should now work with analog input on graphiccards (like ati allinwonder)  

* if Global Visual Range of a render is false it renders all renderobjects lying in the same patch or in one of its subpatches (the latter is new)  
* redundant renderstates aren't passed to directx anymore  
* the procedure of converting older patches is more intelligent (should work right more often)  

## new nodes
* AlphTest (EX9.RenderState) - enable per pixel alpha testing  
*  B-Spline (Value) - retrieves a point on a B-spline curve  
* Clamp (3d) - Clamps points at an axis aligned box.  
*  Delay (Animation) - Delays incoming values for a certain time  
* SwapDim (Spreads) - swaps rows with columns of a 2dimensional matrix of bins. ordering was Bin, Row, Column. ordering will be Bin, Column, Row  
* ZWriteEnable (EX9.RenderState) - enable/disable writing to the depth buffer  
* TexCoords (EX9.TextureState) - For setting advanced texture coordinate creation / transforms (use with cube maps, sphere maps, for projecting textures)  
* Transpose (Transform) - get the transpose of the matrix  
* * (Transform) - multiply two matrix transformations  
* Shear (Transform) - generate a shear transformation.   
* GetMatrix, SetMatrix (Transform) - get or set the 4*4 entries of a matrix by hand  
* * (4d), * (4d Vector) - multiply (x, y, z, w) with 4x4matrix  
* * (3d), * (3d Vector) - multiply (x, y, z, 1) with 4x4matrix (project back to homogenous space)  
* 4x4To3x3 (Traqnsform) - Convert a 4x4 Matrix to 3x3 Matrix. Press F1 on the node.  

* HSB (Transform) - create HSB matrix to perform HSB color transform  
* RGB (Transform) - create RGB matrix to perform RGB color transform  
* LuminanceMatrix (Transform) - multiply luminance matrix with color to convert to greyscale  
* InsertSlice - Insert spreads of a given size into another spread at a specified position  
* Writer(EX9.Textures) - writes a textur to a file. supported formats: .bmp, .jpg, .png, .dds, .dib, .hdr, .pfm  
* DrawFixed : fixed function rendering of a mesh  
* Ex9.Geometry Box: creates Box-Mesh  
* Ex9.Geometry:Sphere: creates Sphere-Mesh  
* Ex9.Geometry:Cylinder: creates Cylinder-Mesh  
* Ex9.Geometry:Teapot: creates Mesh representing the famous Teapot  
* Optimize (Mesh) : controls the reorderig of mesh faces and vertices to optimize performance  
* Count (Mesh): outputs number of subsets, faces and vertices of a mesh  
* VertexDeclaration (Mesh): outputs vertexdeclaration of a mesh's vertexbuffer  
* XFile (Load): loads a XFile and returns a mesh + texture-filename(s), if included in the file  
* DynamicTexture (Color): creates texture dynamically writing input color-spread into the texture  
* DynamicTexture (Value): creates texture dynamically and writes input values into it  
* DynamicTexture (String): creates a texture from a binary-string containing the data of a file of type: .bmp, .dds, .dib, .jpg, .png or .tga  
DirectShow Filter  
* Dump (DShow9): get the mediasample as string  
* Cheater (DShow9): insert before VideoTexture to deinterlace live analog video  
* DScaler (DShow9): see: [www.dscaler.org]  
* Normalize (3d)   

## improved nodes
* FileTexture: has a lot more options now and additionally is capable of loading Cube/Volume Maps  
* Reader (File) only reads on DoRead now. no longer on filenamechanged.  
* I (Spreads) now goes: from .. to-1  
* Queue (Spreads) input spreadable  
* Ord2Enum - now works generic with every enum  
* Queue (EX9.Textures) improved   
* VideoInput - new pins to adjust input size and framerate more precise  
* IOBoxes got Rows, Columns and Pages as Inputs (see inspektor)  
* Self (VVVV) got new Outputs listing the names of the patchs pins  
* Filter (EX9.RenderState) got input to adjust the sharpness of the texture by selecting another MipMap. (MipMap LOD Bias)  
* Cartesian, Polar (3d) - rotation angles made compatible with left handed directx coordinate system. if you look towards an axes then the rotation goes clockwise. pitch, yaw 0 is defined as (0,0,-1)  

## nodes replaced:
* ClientSocket  
* ServerSocket  
* I  
* BarSpread  
* PeakSpread  

## bugs removed:
* filters like Damper, LinearFilter, Newton (..) aren't starting from 0 in new slices but from the first value they receive  
* CAR, CDR in some cases didn't handle their output slicecounts the right way  
* undefined colors (not in the colorroom rgb=000..111) are clamped  

## new modules:
* ApplyTransform (Transform Direction).v4p for transforming not a point at a matrix transformation but a direction. (note that a direction is not influenced by a translation)  
* Arrow (EX9) - draw an arrow to disply a direction  
* SymTex (Transform).v4p - for being able to transform textures on meshes the vvvv way (symmetric). zooming by scaling is always towards the center of the texture, not towards the topleft of the image. (see 4x4To3x3 (Transform) help.v4p)  
## changed modules:
* Camera (Transform Softimage) - now more options and more informations   
* Axis (DX9), AxisAndGrid (DX9) - arrows show in the positive x,y,z directions  
* many  useful help and demo patches added. sort after filedates.  