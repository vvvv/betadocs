---
uid: be2dcaef-c3cb-4f96-80a1-fd861c7f640c
---

# Pixelshader Preparations

For all the pixelshader examples we are using the same basic patch setup featuring a 2x2 <span class="node">Grid (EX9.Geometry)</span> and a <span class="node">FileTexture (EX9.Texture)</span> connected to an effect and the renderers <span class="pin">View Transform</span> scaled by two so that the grid fills the whole view:  

  
![](~/img/01_PixelShaderPreparations_2010.12.19-15.59.56.png "")   
  
Instead of the Template node in the patch we always clone us a new effect as described on the [effects](xref:7aa93595-ec96-4758-8076-0e00e4cf8bf6) page. Connect your newly cloned effect as shown in the patch and open the CodeEditor via a rightclick on the node. Then take the code below and replace it with the templates code as this one is even more simplified leaving out the vertexshader portions which we don't need for now.   

```hlsl  
//texture  
texture Tex <string uiname="Texture";>;  
sampler Samp = sampler_state    //sampler for doing the texture-lookup  
{  
    Texture   = (Tex);          //apply a texture to the sampler
    MipFilter = LINEAR;         //sampler states
    MinFilter = LINEAR;
    MagFilter = LINEAR;
};  

//the data structure: "vertexshader to pixelshader"  
//used as output data with the VS function  
//and as input data with the PS function  
struct vs2ps  
{  
    float4 Pos  : POSITION;
    float2 TexCd : TEXCOORD0;
};  

float4 PS(vs2ps In): COLOR  
{  
    return 1;
}  

technique TSimpleShader  
{  
    pass P0
    {
        VertexShader = null;
        PixelShader  = compile ps_2_0 PS();
    }
}
```  

Press CTRL+S to save/compile the code. No errors should show up. If you get an error at this point make sure you really copied everything and your code in the editor looks exactly as pictured above.  
---  
Next: [Manipulating Colors](xref:cfb2b22c-59c5-4223-b0bd-fee23893ef0d)  
TOC: [Of Effects and Shaders](xref:1f40bd64-bc93-4263-98c8-50616b9f5c5c)  
