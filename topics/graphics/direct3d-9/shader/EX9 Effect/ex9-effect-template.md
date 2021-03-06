---
uid: ba63da26-1207-4876-839d-512b0c34de87
---

# EX9 Effect Template
The Template has the whole effect structure already laid out as code and implements the most basic and working vertex- and pixel-shader. In fact a constant shading with simple texturing.   

The template is structured in 4 sections:  
* Parameters  
* VertexShader  
* PixelShader  
* Techniques  

# Parameter
In the parameter section it first declares the most commonly used transformation matrices via [EX9.HLSL.Semantics](xref:39f956cd-59d0-4445-b87c-57c56affb57c). Note that the variable *tW* which is declared with the *WORLD* semantic appears as a pin on the effect, while the other transformations do not. The *VIEW* and *PROJECTION* semantics assign the respective matrices that are connected to the <span class="node">Renderer (EX9)</span>s <span class="pin">View Transform</span> and <span class="pin">Projection Transform</span> to the *tV* and *tP* matrices.   

Next it declares a texture and a sampler, which has this texture assigned. The last parameter is the texture transformation matrix.  

For every effect you also have to specify which data you want to output from the vertexshader and receive as parameter in the pixelshader. This is most conveniently done via a struct:  

```hlsl, line=0  
struct vs2ps  
{  
    float4 Pos  : POSITION;
    float2 TexCd : TEXCOORD0;
};
```  

Note that this very struct is used as a return parameter for the vertexshader function:  
```hlsl, line=0  
 vs2ps VS(float4 PosO  : POSITION, float4 TexCd : TEXCOORD0)
 {..}
```

and also as the parameter input to the pixelshader function:  
```hlsl, line=0  
 float4 PS(vs2ps In): COLOR
 {..}
```

Using a struct like here is not mandatory. Besides the struct you can pump additional parameters into the pixelshader function as you like.  

In this simple case the struct only carries two values: The position   and texture coordinate vectors. In a realworld effect you'll very likely pass more information from the vertex- to the pixelshader.  

# VertexShader
The templates vertexshader function does not very much. It only fills the output struct with the current vertex position in projection space:  
 Out.Pos = mul(PosO, tWVP);

and the current vertex texture coordinate transformed via the input texture transformation matrix:  
 Out.TexCd = mul(TexCd, tTex);

# PixelShader
The pixelshader function is even simpler. It takes the incoming texture coordinate for this pixel to get the color of the sampler *Samp* at this position and returns it.  

# Techniques
The template effect specifies two techniques. TSimplShader is the cool one, using the shader functions. The other is boring using only fixed function instructions, which you most likely will not need. 