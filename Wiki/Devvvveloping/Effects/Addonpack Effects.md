---
uid: 557d6915-5069-483e-8175-2834225be56b
---

# Addonpack Effects
Here is how you prepare effects for the addonpack:  

## Provide a Shader Info

To provide the nodelist with information about a shader that others find it easier, you should use the following keywords at the beginning of the shader code:  

```hlsl  
//@author: yourname  
//@help: this shader does very nice things  
//@tags: tag1, tag2, tag3 ...  
//@credits: the other guys name
```  

## Creating Pins
Writing a variable in the toplevel of the shader creates an input pin for you. For simple pin names you do not have to do anything special, just start with a capital letter:  

```hlsl  
float Alpha;
```  

Creates a pin named 'Alpha' with default value 0.  
Or:  

```hlsl  
float Alpha = 1;
```  
This will create a pin named 'Alpha' with default value 1.  
In case you have a more complex name for your pin write it like this:  

```hlsl  
float Alpha <string uiname="Alpha of Gradient Center";> = 1;
```  

This will create a pin named 'Alpha of Gradient Center' with default value 1.   
You can also tell the vvvv GUI to constrain the value:  

```hlsl  
float Alpha <float uimin=0.0; float uimax=1.0; string uiname="Alpha of Gradient Center";> = 1;
```  

## Creating Color Pins
Especially when porting shader-code from public libraries you will often notice that a code like  
```hlsl  
float4 cAmb <String uiname="Color";>  = {1, 1, 1, 1};
```  
creates only a float input with 4 slices.  
Just insert the Semantic   
 : COLOR 
to get a 'real' ColorInput.  

```hlsl  
float4 cAmb : COLOR <String uiname="Color";>  = {1, 1, 1, 1};
```  

## Texture Transformations
If you want to transform a texture on a regular shape you would intuitively expect the center of rotation and scaling in the middle of the texture. But the default center of transform is the texture coordinate (0, 0), which is the upper left corner of your texture.  
To counteract this, we provide the convenience sematic 'TEXTUREMATRIX' for you:  

```hlsl  
float4x4 tTex: TEXTUREMATRIX <string uiname="Texture Transform";>;
```  

You should use this semantic every time when you intend to use the transform matrix if this pin to transform texture coordinates.