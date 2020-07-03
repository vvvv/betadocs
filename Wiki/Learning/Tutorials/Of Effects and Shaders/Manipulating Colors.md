# Manipulating Colors

The code we have to concentrate on now is the actual pixelshader function:  

```hlsl, line=20  
float4 PS(vs2ps In): COLOR  
{  
    return 1;
}
```  

Think of this function being called for every pixel of screenspace a mesh occupies in your scene.   

## float4 = color of a pixel
You see that the function has a float4 as a return type. *PS* is the name of the function, could be anything really, it only has to correspond to its mention in the technique block at the bottom of the file.  

The float4 the function has to return is a vector with 4 components making up the color of one pixel. The 4 components are in this particular order:  
* red  
* green  
* blue  
* alpha  

So if instead of the 1 you return a float4 like  
```hlsl  
return float4(1, 0, 0, 1);
```  

your quad will be completely red as the range for each component is between 0 and 1 (not 0 and 255).  

Instead of returning the float4 directly as above you can also define a variable of type float4 first, do something with it and then return the variable, as such:  
```hlsl  
float4 col;  
col = float4(1, 0, 0, 1);  
col /= 2;     //short syntax for: col = col / 2  
return col;
```  
This will result in a darker red as the variable *col* after the division by 2 holds the following values:  
 (0.5, 0, 0, 0.5)
You see that mathematical operations (like the division by 2) on the float4 are applied to all components of the vector at the same time.   
 
## Accessing individual color components/channels
But you can also operate on individual of its components, like so:  
```hlsl  
float4 col = float4(1, 0, 0, 1);  
col.g = col.r / 2;  
return col;
```  
which will result in the following output:  
 (1, 0.5, 0, 1)
Using so called *swizzling* you can access the individual components of a vector. The basic swizzles are .r, .g, .b and .a for the 4 color components, but you can also use them in any arbitrary combination, like:  
 col = col.bgra;
which would reorder the color components of your variable and result in:  
 (0, 0.5, 1, 1)

Really all combinations are allowed with swizzling, even things like:  
.rrgg  
.rb  
.abba  
...you get the idea.  

## Displaying a texture
On the <span class="node">FileTexture (EX9.Texture)</span>'s <span class="pin">Filename</span> choose an image file to your liking.   

To access a texture in a pixelshader and return the color of one of its pixels it needs one line of code:  
```hlsl  
return tex2D(Samp, In.TexCd);
```  
Here we directly return the result of the function *tex2D* (which is a float4) as the pixels color. The function takes a sampler as its first parameter and a texture coordinate as its second input.   

Doubleclicking any word in the editors text marks all the occurances of this word, so by doubleclicking the sampler variable *Samp* you see that it is defined on the very top of the file. A sampler is a structure that combines a texture and some sampler states. We'll leave it at that for the moment and also only care about the texture coordinates later.   

Now lets play a bit with the color channels of the texture:  
```hlsl  
float4 col = tex2D(Samp, In.TexCd);  
return col.bgra;
```  
Here we are first sampling the color of an image assigning it to a variable called *col*. Instead of simply returning *col* as the current pixels color we are switching the red and blue color channels and return that.  

```hlsl  
float4 col = tex2D(Samp, In.TexCd);  
return col.b;  //short syntax for: return float4(col.b, col.b, col.b, col.b)
```  
or we can also view only the blue component of the image applied to all 4 color channels.   

## Inverting a texture
In order to invert a texture we want to only invert the red/green/blue components but leave the alpha channel as is, like this:  
```hlsl  
float4 col = tex2D(Samp, In.TexCd);  
col.rgb = 1 - col.rgb;  
return col;
```  

## Contrasting a texture
The contrast of an image can be increased by increasing all color values greater than 0.5 and decreasing all below 0.5. In order to do so we first move the value range down by 0.5 so we can do a symmetric scaling in both directions (around 0) via a simple multiplication with the Contrasting factor. Then bring the range up to 0..1 again.  

```hlsl  
float4 col = tex2D(Samp, In.TexCd);  
col.rgb -= 0.5;  
col.rgb *= Contrast;  
col.rgb += 0.5;  
return col;
```  
Saving this will result in an error:  
 undeclared identifier 'Contrast'
as we haven't defined it yet. so just above your pixelshader function write:  
 float Contrast = 1;
to define a variable named *Contrast* and initialize it with the value 1. Save. Note how this automatically results in a new pin called *Contrast* on your effect node. Changing the value of this pin changes the contrast of the image.  

## Converting to grayscale
As <a href="http://en.wikipedia.org/wiki/Grayscale#Converting_color_to_grayscale" class="extURL" target="_blank">the internet</a> tells us there is a simple formular to convert a color into its corresponding grayscale value by taking the perceived lightness of each of the 3 color channels into account. The idea is to add together 30% of the red value, 59% of the green value, and 11% of the blue value. This can be done in two ways:  
```hlsl  
float4 col = tex2D(Samp, In.TexCd);  
col.rgb = col.r * 0.3 + col.g * 0.59 + col.b * 0.11;  
return col;
```  
The more elegant way would be using the [dot product](TODO INTERNALLINK:3d-vector-mathematics#dot-product) between two vectors:  
```hlsl  
const float3 lumCoeff = {0.3, 0.59, 0.11};  
col.rgb = dot(col.rgb, lumCoeff);
```  
which does (mathwise) exactly the same thing as the lines above.  

## Reusing code in functions
Say we want to use the conversion of a pixel to its corresponding gray value more than once in our code. Instead of writing the same code twice we can extract the grayscale conversion code into a separate function we can reuse at will. So we create a new function called *ConvertToGray* that returns a float4 and takes a float4 as parameter:  
```hlsl  
float4 ConvertToGray(float4 col)  
{  
    const float4 lumcoeff = {0.3, 0.59, 0.11, 0};
    return dot(col, lumcoeff);
}
```  
We'd use this function in the main pixelshader function like:  

```hlsl  
float4 col = tex2D(Samp, In.TexCd);  
return ConvertToGray(col);
```  

Voila. Now fasten your seatbelts!  
---  
Next: [Texture Coordinates](TODO INTERNALLINK:Tutorial Effects - Texture Coordinates)  
Back: [Pixelshader Preparations](TODO INTERNALLINK:Tutorial Effects - Pixelshader Preparations)  
TOC: ((Tutorial - Of Effects and Shaders|Of Effects and Shaders))