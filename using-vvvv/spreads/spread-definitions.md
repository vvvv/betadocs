---
uid: a2b935e8-17cd-4c26-b701-4919803792d1
---

## Terms

**Spread** -  A one dimensional list (array) of data  
**Slice** -  One element of a spread  
**Bin** -  A virtual subset of consecutive slices in a spread  
**NIL** -  A spread of 0 slices, depicted as Ø  

**Slice Count** -  Number of slices in a spread  
**Spread Count** -  Synonym to Slice Count  
**Bin Size** -  A number that specifies how many consecutive slices of a spread together form a bin  
**Index** -  A number referencing a slice via its position in a spread. Counting from 0.  


## Spreads and Slices

![](~/img/Modulo.png "")   

## Nil

![](~/img/NIL.png "")   


Not to be confused with:  
* a value-spread of one slice containing the "0"  
* a string-spread of one slice containing zero characters  

As a rule of thumb: If any of a nodes inputs contains *nil*, its output also returns *nil*. Rendernodes like the <span class="node">Quad (EX9)</span> with a nil input are not drawn.  


If you want to create nil, use: <span class="node">NIL (Spreads)</span>.  
If you want to avoid it, use: <span class="node">AvoidNIL (Spreads)</span> or a <span class="node">S+H (Animation)</span> only sampling when the incoming value is not Ø.  




## Bins and Bin Sizes

A <span class="pin">Bin Size</span> always refers to an other input on the same node and provides information as to how that other inputs spread is structured.  

For nodes that have a <span class="pin">Bin Size</span> and an <span class="pin">Index</span> note that the *Index* refers to bins rather than the individual slices!  


If you want to provide a <span class="pin">Bin Size</span> as an input to your own subpatch/module make sure to use one of the <span class="node">NormalizeBinSize (Value)</span> convenience nodes which turns any given binsize (positve/negative) into a spread of positive binsizes for easier handling.  


![](~/img/BinSize.png "")   

![](~/img/BinSizeModulo.png "")   



Note that you can also specify a spread of positive (not negative!) BinSizes which essentially means that you can have a "spread of spreads" where each "inner" spread can have a different count.  