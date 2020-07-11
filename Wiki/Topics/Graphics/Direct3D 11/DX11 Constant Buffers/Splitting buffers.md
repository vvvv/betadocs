---
uid: 9c3d6ba1-935b-4109-b6ae-6967953970db
---

#  Splitting buffers

So as we said, and since we are allowed to use several of those buffers, we now split all of those in that way:  

```  
cbuffer cbPerRender : register( b0 )  
{  
	float4x4 tVP : VIEWPROJECTION;
	float4x4 tP : PROJECTION;
};  

cbuffer cbPerObject : register (b1)  
{  
	float4x4 tW : WORLD;
	float4x4 tWVP : WORLDVIEWPROJECTION;
	float Alpha <float uimin=0.0; float uimax=1.0;> = 1; 
	float4 cAmb <bool color=true;String uiname="Color";>;
	float4x4 tTex <string uiname="Texture Transform"; >;
	float4x4 tColor <string uiname="Color Transform";>;
};  

```  

Now shader node will react like that:  
* Notice that everything in cbPerRender is provided by renderer  
* Update buffer once  
* Then run the same loop as above, but only updating b1  

So that gives us a total of:  
64 * 2 (once) 
64 * 4 + 16 + 4 = 276 (per element)

For he same amount of calls, we end up with 141440 bytes uploaded instead.  

Compared to the above version that's a decent gain.  

Please note that also, normally the effects runtime will notice that cbPerRender is not used by pixel shader and in that case will no bind it (saves you an API call as well).  

