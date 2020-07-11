---
uid: f86bc304-0644-46b2-bf51-e265e840babf
---

# Effect Compiler Changes
Since **beta26** vvvv uses a new compiler for effects which is more picky (but also considerably faster) than the one used before. So if you have an effect that worked before but now fails to compile with betas>=26 try the following:  

* when using Shader Model 3 make sure to set both vertex- and pixelshader to use this profile:  
```,lang=hlsl:  
VertexShader = compile vs_3_0 VS();  
PixelShader  = compile ps_3_0 PS();  

```  

* change all references from the type *double* to *float*:  
```,lang=hlsl:  
float = 3.1415; //was: double = 3.1415;  
float2 = 0;     //was: double2 = 0;  

```  

* make sure you don't have functions that have the same name as a technique:  
```,lang=hlsl:  
float3 SteinbachScrew  
{  
 ..
}  

technique SteinbachScrew  
{  
 ...
}  

```  
this will throw an error unless you rename either of the two. For example it is good style to have the technique Start with a capital 'T':  
```,lang=hlsl:  
technique TSteinbachScrew  
{  
 ...
}  

```  
* make sure to not set (ie. write to) global variables. instead define a new local variable to write to:  
```,lang=hlsl:  
float input;  
float3 SteinbachScrew  
{  
 //this will fail 
 input = 0.1; 
 
 //this will work
 input2 = input;
 ..
 input2 = 0.1;
}  

```