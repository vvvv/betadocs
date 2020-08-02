---
uid: 39f956cd-59d0-4445-b87c-57c56affb57c
---

# EX9 HLSL Semantics
Following semantics for parameters in Effect-Files are currently supported in vvvv. All Semantics are case-insensitive.  

**semantic ** | **description** | **type**  
--- | --- | ---  
world | holds the transformation connected to the "Transform" pin. multiply the points of your mesh with that matrix so that you can transform meshes in space. [object space -> world space] | float4x4    
worldinverse  | the inverse of the world matrix [world space -> object space] ***** | float4x4  
worldtranspose   | the transpose of the world matrix ***** | float4x4  
worldinversetranspose | the transpose of the inverse of the world matrix ***** | float4x4  
view   |  this is the transformation you connected to the renderer at pin "View Transform". this matrix normally holds the position and orientation of the camera. multiply the points of your mesh to get them relative to the camera. still no distortion has taken place. after multiplication x goes right, y goes up and z goes into the monitor. [world space -> view space]  | float4x4  
viewinverse   | view-inverse-matrix | float4x4  
viewtranpose   | view-tranpose-matrix | float4x4  
viewinversetranspose   | view-inverse-transpose-matrix | float4x4  
projection   | this is the transformation you connected to the renderer at pin "Projection Transform". it normally holds a perspective transformation. multiply the points of your mesh to distort them by a lens. after multiplication x and y values in between -1 and 1 are visible in the renderer. points wiht z=0 are in front (NearClipping Plane), points with z=1 are behind (Far Clipping Plane). [view space -> projection space] | float4x4  
projectioninverse   | projection-inverse-matrix | float4x4  
projectiontranpose   | projection-tranpose-matrix | float4x4  
projectioninversetranspose   | projection-inverse-transpose-matrix | float4x4  
worldview | world-view-matrix. shortcut to get from [object space -> view space] with one matrix multiplication ***** | float4x4  
worldviewinverse | world-view-inverse-matrix ***** | float4x4  
worldviewtranspose   | world-view-transpose-matrix ***** | float4x4  
worldviewinversetranspose  | world-view-inverse-transpose-matrix ***** | float4x4  
viewprojection  | view-projection-matrix | float4x4  
viewprojectioninverse   | view-projection-inverse-matrix | float4x4  
viewprojectiontranspose   | view-projection-matrix | float4x4  
viewprojectioninversetranspose   | view-projection-inverse-transpose-matrix | float4x4  
worldviewprojection | world-view-projection-matrix. very comfortable matrix to get points from the original mesh relative to the camera and also distorted by its lens. [object space -> projection space]  ***** | float4x4  
worldviewprojectioninverse  | world-view-projection-inverse-matrix ***** | float4x4  
worldviewprojectiontranspose  | world-view-projection-transpose-matrix ***** | float4x4  
worldviewprojectioninversetranspose   | world-view-projection-inverse-transpose-matrix ***** | float4x4  
cameraposition   | the cameraposition | float3  
texturematrix | use this to get a vvvv style symmetric texture transformation | float4x4 (or float3x3)  
viewportindex | the index of the currently drawn viewport | int  
viewportcount | how many viewports the renderer draws | int  
targetsize | size of the rendertarget in pixels | float2  
invtargetsize | 1 / targetsize | float2  
color | use this to get a vvvv style colorpin | float4  



***** if you don`t declare a world-matrix in your effect, but want to make use of any of the world-view-projection-matrices (those matrices you need a world-matrix for to calculate, like "worldview" or "worldviewprojection"), a matrix-pin for the world-matrix will automatically be added (the "Transform Pin") to your effectnode (with the identity matrix as default value).