---
uid: 06cf6b43-dac6-409f-97ec-ff470dd895f0
---

# Specifying colors


![](~/img/vvvv_color-join3.png "")   

<a href="http://en.wikipedia.org/wiki/Color_model#RGB_color_model" class="extURL" target="_blank">RGB color model</a>  
<a href="http://en.wikipedia.org/wiki/HSL_and_HSV" class="extURL" target="_blank">HSL and HSV representation</a>  

#### Related nodes
**Specifiyng Colors**  
<span class="node">RGB (Color Join)</span>  
<span class="node">RGB (Color Join Picker)</span>  
<span class="node">RGB (Color Join Vector)</span>  

<span class="node">HSV (Color Join)</span>  
<span class="node">HSV (Color Join Picker)</span>  
<span class="node">HSL (Color Join)</span>  

<span class="node">AsColor (String Hex)</span>  

**Splitting into components**  
<span class="node">RGB (Color Split)</span>  
<span class="node">RGB (Color Split Vector)</span>  
<span class="node">HSL (Color Split)</span>  
<span class="node">HSV (Color Split)</span>  



Colors in vvvv are represented by 4 color components in a range **0..1**:  
* **R** for Red  
* **G** for Green  
* **B** for Blue  
* **A** for Alpha (defines transparency)  

There is also another way to represent a color in RGB space, which is typically more intuitive to adjust:  
* **HSL** (Hue, Saturation, Lightness)  
* **HSV** (Hue, Saturation, Value) aka HSB.  

The <span class="node">IOBox (Color)</span> uses the HSV representation by default, see [Color IOBoxes](TODO INTERNALLINK:/documentation/ioboxes#color).  

Note, other software packages can specify individual components in another ranges:  
* RGB: 0..255 for the Color channels and 0..100% for the Alpha  
* HSL: 0..360° for the Hue and 0..100% for the Saturation and Lightness.  

Don't forget to convert the values to the 0..1 range.  
There are convenient <span class="node">RGB (Color Join Picker)</span>, <span class="node">HSV (Color Join Picker)</span>and <span class="node">AsColor (String Hex)</span> for helping. Or just type the expression like 270/360 into the IOBox to convert 207° of Hue into 0..1 range.   



