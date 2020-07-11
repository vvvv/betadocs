---
uid: 7c9dc29b-1e01-41d8-b256-618f5d27e939
---

# EX9 Effect File
<a href="http://msdn2.microsoft.com/en-us/library/bb173329(VS.85).aspx" class="extURL" target="_blank">Effects</a> are the direct3d way to combine vertex- and pixelshaders in one file.   

The basic layout of an effect file is as follows:  

>parameters  
functions  

technique1  
  pass1 (vertexshader, pixelshader)
  pass2 (vertexshader, pixelshader)
  ..
 
technique2  
  pass1 (vertexshader, pixelshader)
  pass2 (vertexshader, pixelshader)
  ..

An effect contains parameters that are being used by the functions, the vertex- and pixelshader functions itself and techniques, where you can define with which shaders an object is being rendered and set render and sampler states.  

## Parameters
Parameters are variables, which are declared within an Effect and are either set in the effect directly or from within the application (ie. via the vvvv patch). Parameters can be of any of the <a href="http://msdn2.microsoft.com/en-us/library/bb509587(VS.85).aspx" class="extURL" target="_blank">datatypes defined in HLSL</a>.  

For every parameter defined in an effect vvvv creates an appropriate input pin on the effect node. Via these pins values can be set for parameters from within vvvv.   
#### Semantics
Parameters can be assigned Semantics, which specify how a parameter shall be handled by the effect hosting application (ie. vvvv). For example if you define a parameter of type float4 (vector of 4 floats) and declare it with the semantic "COLOR", vvvv will set up a color input pin at the effect node.   
Via semantics you also have access to the view- and projection matrices (and all of its combinations with the world matrix + transformed and inverse) of the renderer in vvvv. For matrix-parameters declared with one of those semantics no pin will be added to the effect node since those matrices are set automatically by the effect node and thus shall not be visible to the user (except for the world matrix)  

All semantics supported by vvvv are listed on the [EX9.HLSL.Semantics](TODO INTERNALLINK:EX9.HLSL.Semantics) page.   
#### Annotations
For more individual descriptions of parameters you can use [EX9.HLSL.Annotations](TODO INTERNALLINK:EX9.HLSL.Annotations).   

VVVV currently only supports three annotations. The most important to mention is the annotation "uiname" of type string, which defines a name for the pin representing the parameter in the user interface of vvvv (on the effect node). If you don't use this annotation, the pin will just be named like the parameter in the Effect-File.  

## Functions
Like in any modern programming language you can define functions in HLSL to encapsulate/modularize code. Functions in HLSL are declared similar to C/C++/C#. They have a return type, name, input parameters and the function body. An effect can have several functions.   

The main functions of an effect are the VertexShader- and PixelShader functions. From within those other functions can be called.   

#### Vertex Shader
The VertexShader is a function, that is executed for every Vertex of a mesh (geometry/model). In a VertexShader the vertex-processing of the rendering pipeline is implemented, that means: WorldTransform, ViewTransform, lighting and materials and ProjectionTransform. But also more advanced topics such as vertexblending (for animation) or morphing can be realised here.  

#### Pixel Shaders
The PixelShaders is a small function that is executed for every pixel of a mesh. After the model was projected into the 2d-space of the screen and the rasterizer defined each pixel of a mesh, a PixelShader can be run calculating the color for each of those pixels. Advanced per-pixel-lighting and diverse texture operations like filters, transformations, multi-texturing, bump- and normal-mapping can be implemented using PixelShaders.   

## Techniques/Passes
Each effect must contain at least one technique. A technique contains one or several passes. In each pass a vertex and a pixel shader function can be declared, which are then called for the rendering of that pass.   

A default simple technique looks like this:  

```hlsl, line=0  
technique TSimpleShader  
{  
  pass P0
  {
    VertexShader = compile vs_1_1 VS();
    PixelShader  = compile ps_1_0 PS();
  }
}
```  

Here VS() and PS() are the names of the vertex- and pixelshader functions. Instead of defining shaders for the rendering of a pass one could also declare renderstates using the fixed function pipeline, but this is rather oldschool.  

If a technique has several passes, the mesh is rendered once for every pass using its according vertex- and pixelshaders.   

Techniques can provide different versions of an effect. Those can be versions that implement a similar effect for different target GPUs, or simply alternative usable versions of an effect.   