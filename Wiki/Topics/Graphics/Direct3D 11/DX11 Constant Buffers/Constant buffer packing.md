#  Constant buffer packing

You remember when I shown you constant buffer size with all that primary school level calculations... well technically they are all wrong ;)  

GPU wants Constant buffer elements to be aligned on a 16 bytes boundary (yes you know same as when we bitch about using SSE, so yes this is important and yes we want faster transforms ! ;)  

So let's decompose our structure (i'll remove semantic /annotation for clarity)  
```  
cbuffer cbPerObject : register (b1)  
{  
	float4x4 tW; //Offset = 0
	float4x4 tWVP; //Offset = 64
	float Alpha; //Offset = 128
	float4 cAmb; //Offset = 132
	float4x4 tTex; //Offset = 148
	float4x4 tColor; //Offset = 212
};  

Total size : 276  

```  

Actually it is not, let's look at cAmb, offset is 84, which is not a multiple of 16. So your cbuffer will instead be like:  

```  
cbuffer cbPerObject : register (b1)  
{  
	float4x4 tW; //Offset = 0
	float4x4 tWVP; //Offset = 64
	float Alpha; //Offset = 128
	float3 SomeRandomDataAdded ; //Offset = 132
	float4 cAmb; //Offset = 144
	float4x4 tTex; //Offset = 160
	float4x4 tColor; //Offset = 224
};  

Total size : 288  

```  

So technically we got 12 bytes added by runtime.   

This is mostly done for the same reasons as when using SIMD (which I will not cover here), you need your reads to start as 16 bytes boundaries.  

Another way to pack is :  

```  
cbuffer cbPerObject : register (b1)  
{  
	float4x4 tW; 
	float4x4 tWVP; 
	float4 cAmb;
	float4x4 tTex;
	float4x4 tColor;
	float Alpha; 
};  

```  

Which will be... exactly same size (since Constant Buffer size also needs to be a multiple of 16).  

But at least in this case our data is organized in a way that all elements got their start point which is not modified.  

There's also a few other parts that would need to be covered, but let's say that they become more situational (for people interested about manual packing, google packoffset hlsl and you'll be presented with tons of info).  

