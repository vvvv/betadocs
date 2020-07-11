---
uid: efe56243-ca3e-4980-a8cb-8b4e086fdf25
---

# Vertexshader Preparations
 
## Mesh and Vertex
Vertex shaders operate per vertex of a mesh. A vertex is a container for several data fields. These data fields are available in the vertex shader as the input parameter. The most important are the position, texture coordinates and normals. As a shader writer, you have to know what kind of data is stored per vertex. You can use <span class="node">VertexDeclaration (EX9.Geometry Mesh)</span> to get the vertex description for a mesh.  

A mesh container consists of the following data:  

![Mesh Data](~/img/MeshData.png "Mesh Data")   

In vvvv a mesh can be split up in it's data like this:  

![](~/img/MeshData_2010.11.26-13.18.43.png "")   

## Dataflow
To get the whole picture you have to know how the data is processed in the shader. First, vvvv sends all data of this frame to the graphics card, which is:   
* values in the pins of the shader  
* the transformations  
* the mesh  

The vertex shader transforms the vertex positions into the world space and projects them onto the screen (3d world space -> 2d screen space, see [ex9.spaces](TODO INTERNALLINK:ex9.spaces). Depending on the shader it also prepares some other data which is then used in the pixel shader.  
All the data that the vertex shader calculates is packed into a data structure which we call 'vs2ps'. It can have several data fields, which depend on what you need in the pixel shader. It must output the POSITION data field, that the graphics card can calculate which pixels of the screen belong to the mesh. All others are optional, most common is texture coordinates and normals.  
The pixel shader takes the vs2ps as input and is called for each pixel of the mesh to calculate the final pixel color. The values in the vs2ps struct get interpolated for pixels which are located between vertices.  

![Mesh data flow](~/img/MeshDataFlow.png "Mesh data flow")  

See [ex9.dataflow](TODO INTERNALLINK:ex9.dataflow) for more details.  

## Basic Setup
Clone the <span class="node">Template (EX9.Effect)</span> on a patch and connect a mesh to it and render it into a <span class="node">Renderer (EX9)</span>:  

![Basic patch](~/img/Basic_2010.11.26-15.21.26.png "Basic patch")   

then change the code to the following to get a very simple vertex shader setup:  

``` ((lang=hlsl, line=0):  

//transforms  
float4x4 tW: WORLD;        //the models world matrix as via the shader  
float4x4 tV: VIEW;         //view matrix as set via Renderer (EX9)  
float4x4 tP: PROJECTION;   //projection matrix as set via Renderer (EX9)  
float4x4 tWVP: WORLDVIEWPROJECTION; //all 3 premultiplied   

//texture transformation marked with semantic TEXTUREMATRIX  
//to achieve symmetric transformations  
float4x4 tTex: TEXTUREMATRIX <string uiname="Texture Transform";>;  

//the data structure: "vertexshader to pixelshader"  
//used as output data of the VS function  
//and as input data of the PS function  
struct vs2ps  
{  
    float4 Pos  : POSITION;
    float2 TexCd : TEXCOORD0;
};  

//vertex shader  
vs2ps VS(  
    float4 PosO  : POSITION,
    float4 TexCd : TEXCOORD0)
{  
    //declare output struct
    vs2ps Out;

    //transform position
    Out.Pos = mul(PosO, tWVP);
    
    //transform texturecoordinates
    Out.TexCd = mul(TexCd, tTex);

    return Out;
}  

//technique  
technique TSimpleShader  
{  
    pass P0
    {
        VertexShader = compile vs_1_1 VS();
        PixelShader  = null;
    }
}  

```  
---  
Next: [Mr. Wiggle](TODO INTERNALLINK:Tutorial Effects - Mr. Wiggle)  
TOC: [Of Effects and Shaders](TODO INTERNALLINK:Tutorial - Of Effects and Shaders)  
