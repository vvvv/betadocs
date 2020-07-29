---
uid: 2f516214-4f5a-4d2c-af84-2a3dc96dc0c4
---

# Scenarious where Drawing order doesn't matter

## Depthbuffer, Colorbuffer, Normally Blended Opaque Shapes

If you are using a depthbuffer and render your objects in 3d, then you normally don't have to pay attention to the drawing order of your objects. This is handled by the depthbuffer in the following way:  

I know it is hard to think of what is done by the renderer within a frame, because the renderer only presents the result of all the drawing  to you, but still ...   
Let's say you are in the middle of drawing a frame, that is, you already have drawn some objects into the renderer.  
Then an activated depthbuffer means, that for every pixel there is some information available, about how far away that corresponding 3d geometry is. you have to think of this depth info as relative to the camera; you can also think of it as the Z component of a point on the geometry in "projection space".  

When the render now draws the next object on top of it, first the vertexshader is executed to get all the geometry into this projection space (relative to the camera). Now the pixelshader needs only be executed on those pixels which belong to 3d objects that will be in front of the stored depth value.  

At the end it doesn't matter in what order you have drawn the objects. You will always see those parts of 3d geometry which are nearest to you (at the respective pixels).  

All the pixels together are also called the colorbuffer. So we can describe a renderer or a connected DX9Texture as a combination of a colorbuffer and a depthbuffer.  

The mathematican would describe that behaviour (that the order of drawing doesn't matter) as commutativity of that drawing operation.  

So let's try to describe it formally:  

 showNearestOnly ( (C1, D1), (C2, D2) ) = showNearestOnly ( (C2, D2), (C1, D1) ) 

where C and D relate to color and depthinfo of a pixel.  

Think of C1 and D1 are the color and depth info of a pixel already stored in colorbuffer and depthbuffer and C2 and D2 are color and depth info of the geometry just running through the rasterizer at that same pixel.   

 showNearestOnly:
 if D2 <= D1 
   then D=D2 C=C2
   else D=D1 C=C1 (keep the old depth and color info)

Note that this showNearestOnly (i invented that name to summarize the behaviour) only works in that simplified way, when you   
* keep the default blend mode. (or connect a Blend with DrawMode: Blend)   
* keep the default zcompare mode. (or connect a ZWriteEnable with Compare Function: LessEqual)  
* don't work with alpha.  


Just for fun or completeness there is some sort of proof for that commutativity at the bottom of the page.   
It shows that this is true for all cases where D1 <> D2. That means: if you draw several objects with the same depth the latest drawn object will be visible (and therefore the drawing order in this case matters).  
ZWriteEnable has a pin for tweaking that behaviour (Depth Bias; check the directx manual for more details, come back and write it here)  


## Add mode. Another commutative scenario

If you don't work with a depthbuffer, and turn the blend mode for **all** objects (e.g. with GlobalRenderState) to add, then you have another commutative case (you don't have to care about drawing order).  

adding things up is always commutative:  
 
 C1 + C2 = C2 + C1

note that we don't have to care about D because we don't have a depthbuffer.  

in the early days of vvvv this was the default setting.  

note that you **also can use alpha** in that scenario:  

 C1*A1 + C2*A2 = C2*A2 + C1*A1


## Multiply mode. Another commutative scenario

Again no depthbuffer.   

 C1 * C2 = C2 * C1

note that i assume again that all objects are drawn with multiply mode (Blend node). alpha is not supported here.  

you would normally start with a bright background and also keep shapes relatively bright. (just for the beginning)  


## Multiply mode with alpha. Another commutative scenario

If you want to support alpha textures and preserve the commutative case, then one possibility would be to do an operation in the pixelshader, which encodes the alpha in the output color (rgb channels). (however this way you still don't get a transparent renderer output, if that would be your goal)  

just a suggestion for that equation in the pixelshader:  

if alpha of the pixelshader output   
* **is 0** then this should not affect the color of the pixel already in the colorbuffer. **output 1** (that is white; when multiplied with the pixel in the colorbuffer doesn't affect its color)  
* **is 1** then this should not affect the output color of the pixelshader. just **output C** (the rgb channels shouldn't be affected)  

from within the pixelshader (last lines before return):  
 col.rgb = lerp(1, col.rgb, col.a);
 col.a = 1; 
 
since the output of the pixelshader can still be described just with C2 (no alpha is used in multiply blend mode), we don't have to prove that this is still commutative.  

note that i assume again that all objects are drawn with multiply mode (Blend node).  


# A Closer Look 

## A detailed look on the blend operations (Blend Advanced)

We described the pixel already in the colorbuffer with C1, A1 and the output of the pixelshader as C2, A2.  

The Blend Advanced node refers to the colorbuffer as the destination and the pixelshader output as the source.   

The output of the blending operation can be descibed as:  

 C = C1 * DestinationBlendMode + C2 * SourceBlendMode

### The default blend mode:
 
 Source Blend Mode = SrcAlpha
 Destination Blend Mode = InvSrcAlpha
 
 C = C1 * InvSrcAlpha + C2 * SrcAlpha 
   = C1 * (1-A2) + C2 * A2 

In the first chapter we just looked at opaque shapes (A2=1). Then this simplifies to  
 C = C2

for all pixels which passed the depth test...  

### The default add mode:

 Source Blend Mode = SrcAlpha
 Destination Blend Mode = One
 
 C = C1 * One + C2 * SrcAlpha
   = C1 + C2*A2

note that A1 is already encoded in C1...?!  
hm... sorry for that...  
 C = add(add(background, shape1), shape2) = add(background + c1*a1, shape2) 
   = background + c1*a1 + c2*a2
   = background + c2*a2 + c1*a1

### The default multiply mode:

 Source Blend Mode = DestColor
 Destination Blend Mode = Zero
 
 C = C1 * Zero + C2 * DestColor
   = C2 * C1


## Where Drawing Order Matters

### Transparency and Depthbuffer

So here is the interesting part.  
If you want to use transparency and the default blend mode, then you should at first draw all the opaque shapes, where the drawing order doesn't matter.  
After that draw the transparent shapes on top (the depthbuffer will ensure that only those which are nearest to you will be seen).  
This is necessary because the default blend is not commutative for A2<>1.  

However you also have to somehow ensure that if you draw several transparent shapes, that they are ordered from back (large Z value in projection space) to front (smaller Z value in projection space).  

The best would be to do that for every pixel in the resulting image.  
This is called depth peeling and is somehow expensive and challenging.   
There are papers about it, but i know of no vvvv user, who tried that yet. I also found [ftp://ftp.research.microsoft.com/pub/tr/TR-2006-81.pdf|a document] about how to do it with multiple render targets (which is supported by the latest version of vvvv) which looks promissing at a first glimpse.  

Hacks which should be faster but not so precise:  

### Sort a Spread of Shapes in Projection Space

If you have all your transparent shapes in one big spread, and know that these shapes normally don't intersect each other, then you can sort all the slices in zorder and draw them from back to front.  

You therefore need to multiply the centers/positions of the shapes with the ViewProjection Matrix (which is View*Projection). If you're using the softimage camera then just take that ViewProjection Transform output.  
The multiplication can be done with *** (3d Vector)**.  

Sort the outcoming Z value with a **Sort** node, **Reverse** the former indices to get the indices of the shapes from big Z to small Z (far to near), and then use a **GetSlice (Node)** to sort the transformations. Note that you should then also sort all the other parameters going to the shader (like textures, colors,   
...) to get all consistent again.  

### A single 3d shape

Note that even a such a simple shape like a transparent sphere causes problems.  
It has front and back side and if you want to draw it from back to front you have to take care that you first draw the back side (inner side) and then the front side.  
You can do that by spreading a Cull node.   
Use the Clockwise to draw the inner/back side and then CounterClockwise to draw the side facing the camera.  

### todo:
* think/talk about mixing add and blend mode when using a depthbuffer.   
* depthpeeling in detail  
* what more?  
* simplify  
* discuss other blend modes  
* discuss ZWriteEnable in detail  
* discuss AlphaTest  
* rename wikipage  
* add patches and effects  


---  
##  Proof for showNearestOnly is commutative

we stated that  
 showNearestOnly ( (C1, D1), (C2, D2) ) = showNearestOnly ( (C2, D2), (C1, D1) )

lets be more clear what the result of showNearestOnly is:  
 (C, D) = showNearestOnly ( (C1, D1), (C2, D2) ) 

it is just a pair of a new color and a new depth value for that pixel.  

so lets see what the left part of the equation gives:  

 showNearestOnly ( (C1, D1), (C2, D2) ) 
 = ( if D2 <= D1  then D=D2 C=C2  else D=D1 C=C1 )

the right part:  

 showNearestOnly ( (C2, D2), (C1, D1) )
 = ( if D1 <= D2  then D=D1 C=C1  else D=D2 C=C2 )

lets transform the right part until it is equal to the left part:  

 = ( if D2 >= D1  then D=D1 C=C1  else D=D2 C=C2 )

here we just reformulated the if-argument without changing its semantics.  

 = ( if D2  < D1  then D=D2 C=C2  else D=D1 C=C1 )

here we NOT-ed the argument of the if-statement and at the same time flipped the then and else branches, which also doesn't change semantics of the whole expression.  

 = showNearestOnly ( (C1, D1), (C2, D2) ) 
 for all D1 <> D2 

if we compare this expression with the left part equation, then we see that they are equal for all D1<>D2...