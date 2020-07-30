---
uid: 585532e3-3a74-45f0-8925-293b6ba4e868
---

#  To Spread or not to Spread?

Now another important thing is that the shader node will also check if your input pin is spreaded or not.  

If pin is not spreaded that part of the buffer will be only updated once (same as PROJECTION for example)  

So now let's say tColor is always the same, so is cAmb (eg: always single spread count).  

You can modify your buffers like this:  


```  
cbuffer cbPerRender : register( b0 )  
{  
	float4x4 tVP : VIEWPROJECTION;
	float4x4 tP : PROJECTION;
	float4x4 tColor;
	float4 cAmb;
};  

cbuffer cbPerObject : register (b1)  
{  
	float4x4 tW : WORLD;
	float4x4 tWVP : WORLDVIEWPROJECTION;	
	float4x4 tTex;
	float Alpha;
};  

```  

Here since the shader node will know that tColor and cAmb are single spread,  buffer will be uploaded only once.  

BUT (and this is IMPORTANT):  
If now you spread cAmb pin, cbPerRender will be updated EVERY frame again. So you go back to point 0.  

So make sure that you always only combine elements which will have a single count.  

Please note that in next major release(s) for dx11 nodes that fact will become even more important (and please bitch about .NET 4.5 framework support :)  

