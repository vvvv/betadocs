# Texture Transformation
## Primitives
Note that all of the primitives like <span class="node">Quad (DX9)</span>, <span class="node">Segment (DX9)</span>,... have a <span class="pin">Texture Transform</span> next to the <span class="pin">Transform</span>. If you want to position/scale/rotate the texture on a primitive (instead of the primitive itself) you best connect a <span class="node">Transform (Transform 2d)</span> node to the <span class="pin">Texture Transform</span>. Like this you can achieve all desired transformations.   

Also note the <span class="pin">Sampler State</span> which accepts <span class="node">Filter (EX9.SamplerState)</span> and <span class="node">Address (EX9.SamplerState)</span> the latter of which is also interesting in connection with texture transformations. It allows you to specify how a texture is drawn outside of its own borders, ie. when a texture is scaled smaller. The address mode can be specified for U and V (ie. horizontal and vertical direction) separately and take one of 5 options:  
* Wrap - simple repeat  
* Mirror - repeating with every second version being flipped  
* Clamp - repeating only the last pixel  
* Border - allows to specify a border color via <span class="pin">Border Color</span>  
* MirrorOnce - mirrors once, then clamps  


## Effects
Most effects have a <span class="pin">Texture Transform</span> as well but they don't have a <span class="pin">Sampler State</span>. If you want to use a special sampler state on an effect you can only do that in its code, which is easy. First rightclick an effect and save a local copy via Ctrl+S. Now locate the sampler state block, which typically looks something like this:  

```  
sampler Samp = sampler_state  
{  
    Texture   = (Tex); 
    MipFilter = LINEAR;
    MinFilter = LINEAR;
    MagFilter = LINEAR;
};  

```  

Here you can now add addressmodes and a bordercolor, like  
```  
sampler Samp = sampler_state   
{  
    Texture   = (Tex);          
    MipFilter = LINEAR;         
    MinFilter = LINEAR;
    MagFilter = LINEAR;
    AddressU = BORDER;
    AddressV = MIRROR;
    BorderColor = float4(1, 0, 0, 1); //red border
};  

```