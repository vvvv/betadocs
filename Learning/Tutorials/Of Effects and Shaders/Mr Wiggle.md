---
uid: fe316c6e-bcd0-44e0-bde8-9e987e56bc5c
---

# Mr Wiggle

Lets start with the famous MrWiggle effect, it distorts a mesh by sine waves:  

The vertex shader is called for each vertex of the mesh. As you have learned [here](xref:efe56243-ca3e-4980-a8cb-8b4e086fdf25), the input of the vertex shader is the data stored in the vertex of the mesh which is now processed:  

``` ((lang=hlsl, line=0):  
vs2ps VS(  
    float4 PosO  : POSITION,
    float4 TexCd : TEXCOORD0)
{  
...  
}  

```  

Here we are interested in the PosO vector, which is the position of the current vertex. We will add an offset to the x coordinate of the vertex depending on its vertical position (y coordinate):  

```hlsl  
PosO.x += sin(PosO.y);  

```  

To control the waves we add some parameters:  

```hlsl  
PosO.x += sin(PosO.y * Frequency + Phase) * Amplitude;  

```  
Then the vertex shader with its inputs looks like:  
```hlsl  
float Frequency = 10;  
float Phase = 0;  
float Amplitude = 0.01;  

vs2ps VS(  
    float4 PosO  : POSITION,
    float4 TexCd : TEXCOORD0)
{  
    //declare output struct
    vs2ps Out;
    
    //offset x coordinate
    PosO.x += sin(PosO.y * Frequency + Phase) * Amplitude;

    //transform position
    Out.Pos = mul(PosO, tWVP);
    
    //transform texturecoordinates
    Out.TexCd = mul(TexCd, tTex);

    return Out;
}  

```  
And the patch accordingly:  

![mr wiggle patch](~/img/Basic_2010.11.26-17.09.16.png "mr wiggle patch")   
---  
Next: [Function Printing](xref:3673bac8-2d38-4de1-8d09-e1e23109b9ad)  
Back: [Vertexshader Preparations](xref:efe56243-ca3e-4980-a8cb-8b4e086fdf25)  
TOC: [Of Effects and Shaders](xref:1f40bd64-bc93-4263-98c8-50616b9f5c5c)  

