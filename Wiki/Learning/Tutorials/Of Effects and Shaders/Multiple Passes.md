---
uid: 39838eb2-c610-47d7-ad8f-79c7bdb2cda4
---

# Multiple Passes
 
While effects can have multiple passes per technique as outlined in [EX9.Effect.File](TODO INTERNALLINK:EX9.Effect.File) there is no way (in vvvv) to access the color returned in the pixelshader of pass 1 in pass 2. For such kind of multipass effects we need to go the round via <span class="node">Renderer (EX9)</span> and using its output as a texture via <span class="node">DXTexture (EX9.Texture)</span> as an input to another effect.  

## Effect Chain
As promised in [Neighbouring Pixels](TODO INTERNALLINK:tutorial effects - neighbouring pixels) here is how to chain the horizonal and vertical blurs in a way to achieve a perfectly smooth blur in both directions.  
  
![](~/img/multipass_1.png "")   
  
The ouput of renderer *Pass 1* is taken as a texture whose resolution is set to correspond to the original image. This texture is taken as input to the vertical blurring effect in *Pass 2*. Like this you can chain any number of effects.   

## Feedback
Using this technique you can of course also create effects that take the output they create back via a texture input, thus creating a feedback.   

An example for such an application would be <a href="http://en.wikipedia.org/wiki/Cellular_automaton" class="extURL" target="_blank">Cellular Automata</a> the most popular of which is <a href="http://en.wikipedia.org/wiki/Conway%27s_Game_of_Life" class="extURL" target="_blank">John Horton Conway's "Game of Life"</a>.  

  
![](~/img/07_MultiplePasses_2-DirectXRenderer_2010.12.19-16.07.55.png "")   
  

Rather than a game it is actually more a simulation based on a grid of cells (much like pixels of a texture) that can either be dead (black) or alive (white). The simulations result is essentially a black texture with some white pixels. Using the result as a starting point for the next generation of the simulation creats a feedback and lets the simulation run forever. Of course this needs an initial state to start from which is realized in this example using the mouse to add living cells, see the according patch in <a href="https://vvvv.org/contribution/of-effects-and-shaders" class="extURL contribution" target="_blank">of-effects-and-shaders</a>  

The *Game of Life* has 3 simple rules:  
* A dead cell with exactly three live neighbors becomes a live cell (birth).  
* A live cell with two or three live neighbors stays alive (survival).  
* In all other cases, a cell dies or remains dead (overcrowding or loneliness).  

So in the pixelshader for every pixel we have to count its living neighbours and decide according to the rules if the pixel will live or be dead in the next generation.   

``` (lang=hlsl):  
float2 PixelSize;  
float4 PS(vs2ps In): COLOR  
{  
	//sample the current pixel
	float4 center = tex2D(Samp, In.TexCd);
	
	//prepare pixel offsets for x and y
	float2 offX = float2 (PixelSize.x, 0);
	float2 offY = float2 (0, PixelSize.y);
		
	//sample neighbours and add up their states
	float alive = 0;
	alive += tex2D(Samp, In.TexCd - offY).r;
	alive += tex2D(Samp, In.TexCd - offY - offX).r;
	alive += tex2D(Samp, In.TexCd - offY + offX).r;
	alive += tex2D(Samp, In.TexCd + offY).r;
	alive += tex2D(Samp, In.TexCd + offY - offX).r;
	alive += tex2D(Samp, In.TexCd + offY + offX).r;
	alive += tex2D(Samp, In.TexCd - offX).r;
	alive += tex2D(Samp, In.TexCd + offX).r;

	//a dead cell with exactly three live neighbors becomes a live cell (birth).
	if (center.r == 0 && alive == 3) 
	{
	  center.rgb = 1;
	} 
	//a live cell with two or three live neighbors stays alive (survival).  
	else if (center.r == 1 && (alive == 3 || alive == 2)) 
	{
	  center.rgb = 1;
	} 
	//in all other cases, a cell dies or remains dead (overcrowding or loneliness).
	else 
	{
	  center.rgb = 0;
	}

	return center;
}
```  

Another important thing to notice in the effect are the sampler state settings:  

``` (lang=hlsl):  
sampler Samp = sampler_state    //sampler for doing the texture-lookup  
{  
    Texture   = (Tex);          //apply a texture to the sampler
    MipFilter = NONE;         //sampler states
    MinFilter = POINT;
    MagFilter = POINT;
};
```  
Note how all the filtering is disabled. This allows the truely working with unique pixels and not letting the graphiccard interpolate between pixels which would make no sense in this application where a pixel must only be black or white, but no shade gray.  

---  
Next: [Vertexshader Preparations](TODO INTERNALLINK:Tutorial Effects - Vertexshader Preparations)   
Back: [Multiple Textures](TODO INTERNALLINK:Tutorial Effects - Multiple Textures)  
TOC: ((Tutorial - Of Effects and Shaders|Of Effects and Shaders))