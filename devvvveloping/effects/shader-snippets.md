---
uid: df17e4b0-784e-4d81-bcc7-bd88f50e1cb5
---

# Shader Snippets
Why reinvent the wheel? There're some handy little functions for the everyday HLSL writer. Please add your snippets in this wiki page.  



# General snippets
## get clipping planes of a Perspective Projection
```hlsl  
float4x4 tPI: PROJECTIONINVERSE;  
float FarPlane = 1 / (tPI[2][3] + tPI[3][3]);  
float NearPlane = 1 / distance(tPI[2][3], tPI[3][3]);
```  

# VertexShader snippets 
## apply rotation to vertices via texture

rotation function:  
```hlsl  
float4x4 Vrotate(float rotX,   
		 float rotY, 
		 float rotZ)
  {
   rotX *= TwoPi;
   rotY *= TwoPi;
   rotZ *= TwoPi;
   float sx = sin(rotX);
   float cx = cos(rotX);
   float sy = sin(rotY);
   float cy = cos(rotY);
   float sz = sin(rotZ);
   float cz = cos(rotZ);

   return float4x4( cz*cy+sz*sx*sy, sz*cx, cz*-sy+sz*sx*cy, 0,
                   -sz*cy+cz*sx*sy, cz*cx, sz*sy+cz*sx*cy , 0,
                    cx * sy       ,-sx   , cx * cy        , 0,
                    0             , 0    , 0              , 1);
  }

```  

use the function like this:  
```hlsl  
PosO = mul(PosO, Vrotate(Sampler.r, Sampler.g, Sampler.b));  
NormO = mul(NormO, Vrotate(Sampler.r, Sampler.g, Sampler.b));  

```  
Sampler.rgb are the corresponding values from the texture  

## Render to Texture/UV (useful for e.g. texture baking)
Calculate screenspace coordinates based on UV instead of object space and pass it to PS  
```  
Out.Pos = float4((TexCd.xy-0.5)*2*float2(1,-1),0,1);  

```  

# PixelShader snippets for Image processing

## invert
rgb-inversion  
```hlsl   
col.rgb = 1 - col.rgb;
```  

## contrast
```hlsl  
col.rgb = ((col.rgb - 0.5) * var) + 0.5;
```  
if var > 1, the contrast is greater. var = 0 gives a grey picture  
The 0.5 can be replaced with a variable to give a gamma or centre   
point for the contrast as well, for more fine tuning...   
 
## black&white
```hlsl  
const float4 lumcoeff = {0.299, 0.587, 0.114, 0};  
col = dot(col, lumcoeff);
```  
the dot product of the color (col) and the luminace coefficients results in a correct b&w image  

## lumakey
```hlsl  
const float4 lumcoeff = {0.299, 0.587, 0.114, 0};  
float luma = length(dot(col, lumcoeff));  
col.a = step(var, luma);
```  
var is the keying amount. the rest works like the b&w conversion.  

## scene alpha
```hlsl  
return(tex2D(Samp, float2(IN.TexCd.xy)).wwww);
```  
Texture input must be in A8R8G8B8 format.  

## buffer to texture
R:TARGETSIZE;

```hlsl
StructuredBuffer<float4> sb;
float2 R:TARGETSIZE; 
float4 P0(float4 pos: SV_POSITION, float2 uv: TEXCOORD0): SV_Target
{
	return sb[pos.x + (pos.y * R.x)];
}

technique10 Template 
{
	pass P0 <string format="R32G32B32A32_Float";>
	{ SetPixelShader(CompileShader(ps_4_0, P0())); }
} 
```

## working alpha channel in 3d
**needs 2 passes so connect an iobox with 2 rows to the pass pin and fill it with 0,1**  
```hlsl  
technique workingalpha  
{  
    pass P0
    {
        VertexShader = compile vs_1_0 VS();
        PixelShader  = compile ps_2_0 PS();
        AlphaBlendEnable = false;

        AlphaTestEnable = true;
        AlphaFunc = Greater;
        AlphaRef = 245;

        ZEnable = true;
        ZWriteEnable = true;

        CullMode = None;
    }
    pass P1
    {
        VertexShader = compile vs_1_0 VS();
        PixelShader  = compile ps_2_0 PS();
        AlphaBlendEnable = true;
        SrcBlend = SrcAlpha;
        DestBlend = InvSrcAlpha;

        AlphaTestEnable = true;
        AlphaFunc = LessEqual;
        AlphaRef = 245;

        ZEnable = true;
        ZWriteEnable = false;

        CullMode = None;
    }
}
```  

## DX11 Set DepthBuffer
Put this up near the start of your shader  
DepthStencilState DisableDepth  
{  
    DepthEnable = FALSE;
    DepthWriteMask = ZERO;
    DepthFunc = LESS_EQUAL;

    StencilEnable  = FALSE;
};  

and add this when you create the pass  
and SetVertexShader etc  
SetDepthStencilState( DisableDepth, 0 );  


## DX11 Access TextureArray

// declare array of N textures  
Texture2D MyTextureArray[N];  
 
// sample texture of index I from array (0 to N-1)  
MyTextureArray[I].Sample(MySampler, UV);  

##   Will the real texture array please stand up 
note that the above is an array of textures- which is NOT the same thing as a actual texture array!  Example of that below:  

//Control Texture Array  
bool useControlMap;  
Texture2DArray cTex <string uiname="Texture";>;  
SamplerState sam                  //can be set in vvvv  
{  
    Filter = MIN_MAG_MIP_LINEAR; 
    AddressU = Wrap;
    AddressV = Wrap;
};  


float controlTexSample(float2 uv, float iid)  
{  
	float control = 1;
	if (useControlMap) 
	{
		uint d,textureCount; 
		cTex.GetDimensions(d,d,textureCount); 	
		float3 coords = float3(uv, iid % textureCount);	//make sure Instance ID buffer is in floats
		control *= cTex.SampleLevel(sam,coords,0).r;
	}
	return control;
}  


## Set Output-TextureFormat for DX11-TXF-Shader

```  
pass P0 <string format="R32G32B32A32_float";>  
    {SetPixelShader(CompileShader(ps_4_0,fCOLOR()));}

```  

## Defines (or pre-processor directives)

Use pre-processors as in other C inspired languages. These will actually transform the text of your code before compilation.  

```  
1. define MYDEFINE 4
float MyFunc()  
{  
    return MYDEFINE;
}  
// result: 4  

```  
Conditional:  
```  
1. define MYCONDITION 2
float MyFunc()  
{  
1. if MYCONDITION==2
    return 2;
1. else
    return 0;
1. endif
}  
// result: 2  

```  

Check if thing is defined:  
```  
1. define MYCONDITION 2
float MyFunc()  
{  
1. if defined(MYCONDITION)
    return 2;
1. else
    return 0;
1. endif
}  
// result: 2  

```  

## DX11: Define from vvvv
All shader nodes in DX11 (layers, tfx and gfx) have a hidden pin called "Defines" which awaits a spread of string formatted like that:  

```  
DEFINENAME=stuff  

```  

Every time you change the Defines spread shader is recompiled. Example tricks:  

Change tfx pass format without changing the code:  

```  
// define a default value to avoid compilation errors  
1. if !defined(PASSFORMAT)
1. define PASSFORMAT "R8_UNorm"
1. endif

...  

pass P0 <string format=PASSFORMAT;>  
    {SetPixelShader(CompileShader(ps_4_0,fCOLOR()));}

```  
from vvvv:  
```  
PASSFORMAT="R16G16B16A16_Float"  

```
