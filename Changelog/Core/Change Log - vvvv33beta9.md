---
uid: 6b8cdd6e-1c0e-40fb-aa42-34aef294a153
---

# Change Log - vvvv33beta9
released on 01 09 05  

for a list of the most important changes to this release have a look at the extra [beta9](TODO INTERNALLINK:beta9) site.  

## general

* saving patches is always fast  
* fixed bug with pin-inspektors not hiding when value was not changed  
* when entering a value you can now use both ',' and '.' as decimal seperators   
* arguments from Args.txt are now appended to commandline arguments  
* windows can now be toggled 'always on top' (Ctrl+T)  
* new mainloop mode, with defaults to a new mode where the time is filtered to get smoother animations.   
* depth buffer pins are in the Inspector now as enumerations to choose the precision.  
* feedback loops with renderer are much more easier now: create one renderer, write its output texture into the Queue texture (frame count of 1 is sufficient) and use the output of the Queue as a texture in the same renderer.  

## new nodes
* <span class="node">Torus (EX9.Geometry)</span> discrete Render Object, was a module in former versions of vvvv  
* DFT (Value) discrete fourier transform  
* Perlin (2d): smooth 2-dimensional noise function  
* Perlin (3d): smooth 3-dimensional noise function see <a href="http://freespace.virgin.net/hugo.elias/models/m_perlin.htm" class="extURL" target="_blank">Perlin Noise</a>  
* Cross (3d): creates all combination triplets of the inputs  
* MAC (Network): Get the physical MAC address from a given network name or IP (all pins spreadable)  
* Normals (Ex9.Geometry Mesh): calculates normals, tangents, binormals for a mesh  
* Change (Ex9.Geometry Mesh): outputs 1 when the input-mesh changed in this frame, 0 if the input mesh was equal to the one in the last frame  
* Change (Ex9.Geometry VertexBuffer): outputs 1 when the input-vertexbuffer changed in this frame, 0 if the input-vertexbuffer was equal to the one in the last frame  
* Count (Node)  
* Count (Color)  
* Count (Enumerations)  
* IO (Devices IOWarrior40): connect IOWarrior40 by <a href="http://codemercs.com/" class="extURL" target="_blank">code mercenaries</a> to vvvv  

* Buffer (EX9.Texture) creates a spread of textures where new images can be written at arbitrary positions (note that texture input and index input not spreadable yet)  
* Cons (EX9.Texture)  
* AsVideo (DShow9) added: Create DirectShow video stream from texture  
* Writer (DShow9): Write a DirectShow video stream to disk  
* Compress (DShow9): compress a DirectShow video stream with a chosen codec  
* Separate (String): Splits a given string at the selected separator into slices  

## new nodes for complex math
* + (Complex) addition of complex numbers  
* - (Complex) subtraction of complex numbers  
* * (Complex) multiplication of complex numbers  
* / (Complex) division of complex numbers  
* Sqr (Complex) square of a complex number  
* Sqrt (Complex) the square root of a complex number  
* Power (Complex) raise a complex number to the power of a second  
* Cunjugate (Complex) negate the imaginary part of a complex number  
* Abs (Complex) the absolute value of a complex number, the length  
* Arg (Complex) the argument of a complex number, the angle to the real axis   
* Exp (Complex) returns e raised to the power of the input  
* Ln (Complex) complex natural logarithm, returns the exponent of e to reach the input  
* Function (Complex) all complex trigonometric and hyperbolic functions  
* Function (Complex Inverse) all complex inverse trigonometric and hyperbolic functions  
* Function (Complex Special) special complex functions, Sinc, Gamma, Bessel I0 and Bessel J0, note: if you use only the real input of a complex node, the result is also real (ecxept for special cases of Sqrt, Ln and Power) go to <a href="http://en.wikipedia.org/wiki/Complex_number" class="extURL" target="_blank">Wikipedia Complex Number</a> to learn more  

## changed nodes
* MainLoop (VVVV) deleted IncrementMode pin, added TimeMode enumeration pin with: Raw (old mode), Filtered (default) and Increment  
* Gregorian (Astronomy) added Milliseconds output pin  
* CreateNode (VVVV), DeleteNode (VVVV): added 'Query Save' pin to only optionally ask for saving when deleting/removing a changed patch  
* Effect(Ex9.Effect): EnableSliceWise removed; Enable spreadable  
* Optimize(Ex9.Geometry Mesh) now works properly   
* Fog (EX9.Renderstate) now works properly  
* Switch (Value Output), Switch (String Output) fixed   
* Renderers: removed AutoSizeBackbufferPin: a value of 0 now causes autosizing of width and height individually  
* Renderers: added Outputs: ActualBackBufferWidth/Height, IsFullscreen  
* Renderers: changed Pin: FullscreenOnClient to ordinary fullscreen switch pin (finally)  
* TypoSpread: added Spacing pin (1=em). Fixed recalculation bugs. Fixed bug with FillSquare update pin.    
* DynamicTexture (EX9.Texture Color), DynamicTexture (EX9.Texture Value) now work with all texture formats and types  
* Info (EX9.Texture): is now spreadable and added Input: Level and Outputs: Depth, Type   
* Pipet (EX9.Texture) is now spreadable and deals with almost all texture formats, faster  
* Writer (EX9.Texture) is now spreadable  
* ScreenShot (VVVV) renamed to ScreenShot (EX9.Texture) and fixed some minor bugs  

## deleted nodes
* 4x4to3x3 is not necessary anymore.  