---
uid: 3673bac8-2d38-4de1-8d09-e1e23109b9ad
---

# Function Printing

There are various possibilities to alter the vertex positions by mathematical functions.  

For the following examples we use a <span class="node">Grid (EX9.Geometry)</span> as input. Set the resolution to about 50x50.  

##  f(x, y) = z

Create a new z coordinate by x and y. Using [the MrWiggle example](xref:fe316c6e-bcd0-44e0-bde8-9e987e56bc5c) we could write:   

```hlsl  
float2 Frequency = 10;  
float2 Phase = 0;  
float2 Amplitude = 0.01;  

vs2ps VS(  
    float4 PosO  : POSITION,
    float4 TexCd : TEXCOORD0)
{  
    //declare output struct
    vs2ps Out;
    
    //calculate two waves
    float2 wave = sin(PosO.xy * Frequency + Phase) * Amplitude;
    
    //set z coordinate
    PosO.z = wave.x + wave.y;

    //transform position
    Out.Pos = mul(PosO, tWVP);
    
    //transform texturecoordinates
    Out.TexCd = mul(TexCd, tTex);

    return Out;
}  

```  

using a patch like:  
![function patch](~/img/FunctionPrint_2010.11.26-19.26.50.png "function patch")  

## f(u, v) = xyz

Another common type is to calculate a completely new position from the xy coordinates of the grid. This is often called parametric surfaces, where the xy input parameters are called uv.  

for example a cone:  

```  
x = v*cos(u)  
y = v*sin(u)  
z = v  

```  

can be written as a function:  

```hlsl  
float3 Cone(float2 uv)  
{  
	float u = uv.x;
	float v = uv.y;
    
	float3 newPos;
	newPos.x = v * cos(u);
	newPos.y = v * sin(u);
	newPos.z = v;
	
	return newPos;
}  

```  
It might be handy to scale u by two pi to get a full cycle in the range 0..1, as well as have a general offset and scale for the input parameters. The vertex shader could then look like:  

```hlsl  
1. define twopi 6.28318531

float2 Scale = 1;  
float2 Offset = 0;  

float3 Cone(float2 uv)  
{  

 	uv *= Scale;
 	uv += Offset;
 
	float u = uv.x * twopi;
	float v = uv.y;
    
	float3 newPos;
	newPos.x = v * cos(u);
	newPos.y = v * sin(u);
	newPos.z = v;
	
	return newPos;
}  

vs2ps VS(  
    float4 PosO  : POSITION,
    float4 TexCd : TEXCOORD0)
{  
    //declare output struct
    vs2ps Out;
    
    //set new position
    PosO.xyz = Cone(PosO.xy);

    //transform position
    Out.Pos = mul(PosO, tWVP);
    
    //transform texturecoordinates
    Out.TexCd = mul(TexCd, tTex);

    return Out;
}  

```  

And the patch:  
![cone patch](~/img/FunctionPrint_2010.11.26-20.51.15.png "cone patch")   
---  
Next: [Vertex Data](xref:b36fb6d0-734d-4f7f-b213-d47dc9d90169)  
Back: [Mr. Wiggle](xref:fe316c6e-bcd0-44e0-bde8-9e987e56bc5c)  
TOC: ((Tutorial - Of Effects and Shaders|Of Effects and Shaders))