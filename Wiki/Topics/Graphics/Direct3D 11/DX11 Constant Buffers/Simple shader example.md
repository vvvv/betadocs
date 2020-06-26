#  Simple shader example

```  
float4x4 tW : WORLD;  
float4x4 tVP : VIEWPROJECTION;  
float4x4 tWVP : WORLDVIEWPROJECTION;  
float4x4 tP : PROJECTION;  
float Alpha <float uimin=0.0; float uimax=1.0;> = 1;   
float4 cAmb <bool color=true;String uiname="Color";>;  
float4x4 tTex <string uiname="Texture Transform"; >;  
float4x4 tColor <string uiname="Color Transform";>;  

```  

This is a basic example (I only show the shader variables to keep things compact).  

Since we don't explicitly manage our data, all of it will automatically be integrated into one of those Constant buffers for you, so this is equivalent to :  

```  
cbuffer cbGlobal : register( b0 )  
{  
	float4x4 tW : WORLD;
	float4x4 tVP : VIEWPROJECTION;
	float4x4 tWVP : WORLDVIEWPROJECTION;
	float4x4 tP : PROJECTION;
	float Alpha <float uimin=0.0; float uimax=1.0;> = 1; 
	float4 cAmb <bool color=true;String uiname="Color";>;
	float4x4 tTex <string uiname="Texture Transform"; >;
	float4x4 tColor <string uiname="Color Transform";>;
};  

```  

Now let's see what we have here:  
* tW : provided by the "Transform In" pin  
* tVP and tP : provided by the Renderer  
* tWVP : which auto combines tW and tVP  
* All the rest will just be input pins.  

Now what we can also notice:  
* tW, tVP, tTex, tP, tWVP will be generally used by vertex shader (let's keep it simple)  
* Rest is used by pixel shader  

But also (and that's the most important):  
* tVP and tP are provided per render. That means that if you draw 1 object or 512 it will stay the same.  
* Rest is on a per slice basis, but...  
* tWVP will be per slice, and will cost you a Matrix Multiply  

Ok so now what happens when we draw our objects (in this scenario):  
Create a structure (in CPU) that is same size of our buffer (with some potential differences, see below)  

Now, for each slice  
* Update structure with pin data  
* Upload constant buffer to your graphics card  
* Assign constant buffer to both Vertex/Pixel shader  
* Draw  
* Repeat  

Now the line that will attract our interest is   
* Upload constant buffer to your graphics card  

Here we have a buffer with a size of:  
64(transform)* 6 + 16 (float4) + 4 (float) = 404 bytes

Now let's say we draw 512 objects, we need the  to upload:  
404*512 = 206848 bytes

In our little simple scenario that's not much, but start to think when you need to start loading more complex structures, skinning transforms...  

So let's modify that a little:  

