# Normals

Besides the position and the texture coodinates, the surface normals are the third important and most commonly used data field of the vertex. The normal is a 3d vector which is perpendicular to the surface curvature at the vertex position.  
The normals are very important for light calculations, when the light vector is reflected on the surface to get the shading of the surface.  

## Displaying normals

VVVV has a helper module to display the surfave normals of a mesh: <span class="node">Normals (EX9)</span>  

We can modify the help patch of it to get a nice view of the mesh with its normals:  

![](~/img/Normals(EX9)help_2010.12.16-21.19.42.png "")![](~/img/Normals(EX9)help-DirectXRenderer_2010.12.16-21.19.45.png "")  


## Calculating normals

If your mesh does not have normals stored with it you can use the node <span class="node">Normals (EX9.Geometry Mesh)</span> to calculate them in the patch before you pass the mesh to the shader. Use the <span class="pin">Smoothing Angle</span> to average the normals at the vertex postion.  

As most shading models (like phong) need the normal in view space, one has to transform the normal along with the vertex position. But you have to take care that the normal is a float3 or if its a float4, the w component of the normal is 0 (instead of 1 for positions), that it only gets rotated, but not translated. A typical vertex shader does the following transformations:  

```hlsl  
    ...
    //normal in view space
    Out.NormV = normalize(mul(NormO, tWV));

    //position (projected)
    Out.PosWVP  = mul(PosO, tWVP);
    ...

```  

## Recalculating normals

It gets more complicated if you change the vertex positions in the vertex shader like we did in the [mr. wiggle](TODO INTERNALLINK:Tutorial Effects - Mr. Wiggle) or the [function printing](TODO INTERNALLINK:Tutorial Effects - Function Printing) tutorial. Because the translation of the vertex positions changes the surface curvature, the normals stored previously in the mesh are not valid anymore. And therefore shading calculations are wrong.  

So, if you need lightning calculations in the pixelshader you have to find a way to recalculate the normals. But this is a very specific problem, which depends on the method that you use to translate the positions.  

The most general, but not so precise way to get the new vertex normal is to calculate 2 additional positions which are close by and get two vectors which are in the tangent plane at this vertex and are not parallel. From the two tangent vectors you can calculate the normal with the cross product:  

--- calc current pos **p**  
--- calc neighbour pos **n1**  
--- calc neighbour pos **n2**  
--- get tangent vector **t1** = **p** - **n1**  
--- get tangent vector **t2** = **p** - **n2**  
--- get normal **n** = **t1** x **t2**  

Using the cone example from the [function printing](TODO INTERNALLINK:Tutorial Effects - Function Printing) tutorial it looks like:  

```hlsl  
float NeighbourOffset = 0.001;  

vs2ps VS(  
    float4 PosO  : POSITION,
    float4 TexCd : TEXCOORD0)
{  
    //declare output struct
    vs2ps Out;
    
    //calc new position
    float3 p = Cone(PosO.xy);
    
    //calc neighbour pos in u direction
    float3 n1 = Cone(PosO.xy + float2(NeighbourOffset, 0));
    
    //calc neighbour pos in v direction
    float3 n2 = Cone(PosO.xy + float2(0, NeighbourOffset));
    
    //get tangent vector 1
    float3 t1 = p - n1;
    
    //get tangent vector 2
    float3 t2 = p - n2;
    
    //get normal
    float3 NormO = cross(t1, t2);
    
    //set new pos
    PosO.xyz = p;
    ...

```  

Now, to actually use the normals we could for example use the Phong function declared in the PhongDirectional.fxh file from vvvv's effects folder. For that, copy the file besides your shader and then have a look into the PhongDirectional.fx shader to get the necessary lines to get the phong shading up and running.  
We need to put the normal, the light and view dir into the view space, and then pass all that in the vs2ps struct to the pixel shader. Let's also copy the code for the texture to get a nice shading setup, where you can just replace the 'Cone' function with all uv-parametric surfaces you can find on the web:  

```hlsl  
// ----------------------------------------------------------------------------  
// PARAMETERS:  
// ----------------------------------------------------------------------------  

//transforms  
float4x4 tW: WORLD;        //the models world matrix as via the shader  
float4x4 tV: VIEW;         //view matrix as set via Renderer (EX9)  
float4x4 tP: PROJECTION;   //projection matrix as set via Renderer (EX9)  
float4x4 tWV : WORLDVIEW;  
float4x4 tWVP: WORLDVIEWPROJECTION; //all 3 premultiplied   

//texture transformation marked with semantic TEXTUREMATRIX  
//to achieve symmetric transformations  
float4x4 tTex: TEXTUREMATRIX <string uiname="Texture Transform";>;  

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
//used as output data of the VS function  
//and as input data of the PS function  
struct vs2ps  
{  
    float4 Pos  : POSITION;
    float2 TexCd : TEXCOORD0;
    float3 LightDirV: TEXCOORD1;
    float3 NormV: TEXCOORD2;
    float3 ViewDirV: TEXCOORD3;
};  

1. include "PhongDirectional.fxh"

// ----------------------------------------------------------------------------  
// VERTEXSHADERS  
// ----------------------------------------------------------------------------  


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

float NeighbourOffset = 0.001;  

vs2ps VS(  
    float4 PosO  : POSITION,
    float4 TexCd : TEXCOORD0)
{  
    //declare output struct
    vs2ps Out;
    
    //calc new position
    float3 p = Cone(PosO.xy);
    
    //calc neighbour pos in u direction
    float3 n1 = Cone(PosO.xy + float2(NeighbourOffset, 0));
    
    //calc neighbour pos in v direction
    float3 n2 = Cone(PosO.xy + float2(0, NeighbourOffset));
    
    //get tangent vector 1
    float3 t1 = p - n1;
    
    //get tangent vector 2
    float3 t2 = p - n2;
    
    //get normal
    float3 NormO = cross(t1, t2);
    
    //set new pos
    PosO.xyz = p;
    
    //put normal in view space and normalize it
    Out.NormV = normalize(mul(NormO, tWV));
    
    //inverse light direction in view space
    Out.LightDirV = normalize(-mul(lDir, tV));
    
    //inverse view dir in view space
    Out.ViewDirV = -normalize(mul(PosO, tWV));

    //transform position (projected)
    Out.Pos = mul(PosO, tWVP);
    
    //transform texturecoordinates
    Out.TexCd = mul(TexCd, tTex);

    return Out;
}  

// ----------------------------------------------------------------------------  
// PIXELSHADERS  
// ----------------------------------------------------------------------------  

float Alpha <float uimin=0.0; float uimax=1.0;> = 1;  

float4 PS(vs2ps In) : COLOR  
{  
	float4 col = tex2D(Samp, In.TexCd);

    col.rgb *= PhongDirectional(In.NormV, In.ViewDirV, In.LightDirV);
    col.a *= Alpha;
  
    return col;
}  

// ----------------------------------------------------------------------------  
// TECHNIQUES:  
// ----------------------------------------------------------------------------  

technique TFunctionWithPhong  
{  
    pass P0
    {
        VertexShader = compile vs_1_1 VS();
        PixelShader  = compile ps_2_0 PS();
    }
}  

```  
TOC: [Of Effects and Shaders](TODO INTERNALLINK:Tutorial - Of Effects and Shaders)  
Back: [Vertex Data](TODO INTERNALLINK:Tutorial Effects - Vertex Data)  
Next: ((tutorial Geometry Morphing|Geometry Morphing))