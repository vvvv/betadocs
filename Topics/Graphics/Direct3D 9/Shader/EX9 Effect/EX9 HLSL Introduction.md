---
uid: 986274a6-3432-428a-9d0a-19ce06e696ff
---

# Semantics
**todo**  

# Vectors and Swizzling
Apart from the simple datatypes like *bool*, *int*, *float* and  *double* with HLSL you can use all those as vectors also, by simply writing something like:  

```hlsl  
float4 ff = {4, 3, 2, 1};  
bool2 bb = {1, 0};
```  

Now you can reach the individual vector components using swizzles, which work as suffixes to the variable names:   
 .x, .y, .z, .w 
are the same as:  
 .r, .g, .b, .a

```hlsl  
float f = ff.a;     // f = 1  
bool b = bb.y;      // b = 0  
float2 f2 = ff.xz   // f2 = {4, 2}
```  

# Arrays
With all the basic datatypes you can also declare arrays, but note that their length is limited, depending on the constant register count of the shader profile used. You can find out about the number of allowed constants on msdn:  
<a href="http://msdn2.microsoft.com/en-us/library/bb172961(VS.85).aspx" class="extURL" target="_blank">vs_2_0 registers</a>  
<a href="http://msdn2.microsoft.com/en-us/library/bb172918(VS.85).aspx" class="extURL" target="_blank">ps_2_0 registers</a>  
<a href="http://msdn2.microsoft.com/en-us/library/bb172963(VS.85).aspx" class="extURL" target="_blank">vs_3_0 registers</a>  
<a href="http://msdn2.microsoft.com/en-us/library/bb172920(VS.85).aspx" class="extURL" target="_blank">ps_3_0 registers</a>  

You can define and access arrays like the following example demonstrates:  
```hlsl  
float4 ff[2] = {{0, 1, 2, 3}, {4, 5, 6, 7}}  
float4 f1 = f[0];        //f1 = {0, 1, 2, 3}  
float3 f2 = f[1].rgb;    //f2 = {4, 5, 6}
```  

# Intrinsic Functions
HLSL has a small list of <a href="http://msdn2.microsoft.com/en-us/library/bb509611(VS.85).aspx" class="extURL" target="_blank">built-in functions</a>. A rightclick in vvvvs shader editor pops up the list.  

# Functions and Includes
Besides the main vertex- and pixelshader functions you can define any number of helper functions in an effect file. If this gets too confusing functions can be outsourced into an extra textfile and linked to from any effect via the <a href="http://msdn.microsoft.com/en-us/library/dd607349%28v=VS.85%29.aspx" class="extURL" target="_blank"># include directive</a> which offers 2 different usages:  
```hlsl  
//local: the referenced file is placed in the same directory as the .fx file which includes it  
1. include "myfunctions.fxh" 

//global: the filename is specified relative to vvvvs root directory  
1. include <effects\myfunctions.fxh>
```

# Shader Profiles
In every technique you have to specify a shader profile with which you want the vertex- and pixelshader functions compiled. Generally speaking, the higher the profile number the more flexible it is. If your shader shows an error regarding that you are out of instructions with the currently set profile you may try one with a higher number.   

Details about shader profiles and corresponding features can be found on msdn: <a href="http://msdn2.microsoft.com/en-us/library/bb509626(VS.85).aspx" class="extURL" target="_blank">Shader Models vs. Shader Profiles</a>  

Depending on the capabilities of your graphic card, vvvv supports the following profiles:  
* vs_1_0, ps_1_0  
* vs_1_1, ps_1_1  
* vs_2_0, ps_2_0  
* vs_2_a, ps_2_a  
* vs_2_b, ps_2_b  
* vs_3_0, ps_3_0 //note that when using vs_3_0 using ps_3_0 is mandatory in vvvv