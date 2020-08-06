---
uid: e911d2aa-cf59-4d41-a11a-f14ed76e9131
---

## An Overview


This is an overview of the most used Spread Operations.   

More operations are available and can be found by querying the [Node Browser](xref:eeb8526d-0085-4219-a138-32ac397853f1) for terms describing the desired operation.  


## Datatype independent operations

Most spread operations are independent of a datatype in that they only shuffle slices around but do not care what data each slice holds. Therefore the nodes mentioned in this section are available in the category of most datatypes.    

Here is a listing of the most common slice operations in their simplest form.   


> **Pro tip:** Any <span class="pin">Index</span> pin is also spreadable! See the helppatches of the respective nodes for more complex usage scenarios.  



![](~/img/SetSlice2.png "")  

![](~/img/SetSpread.png "")  

![](~/img/InsertSlice.png "")  

![](~/img/Reverse.png "")  

![](~/img/Swap.png "")  

![](~/img/Select.png "")  

![](~/img/GetSlice2.png "")  

![](~/img/GetSpread.png "")  

![](~/img/DeleteSlice.png "")  

![](~/img/Shift.png "")  

![](~/img/SwapDim.png "")  


### Combining Spreads

![](~/img/Cons.png "")  

![](~/img/Cross.png "")  

![](~/img/Zip.png "")  


### Splitting Spreads

![](~/img/SplitAt.png "")  

![](~/img/Pairwise.png "")  

![](~/img/Unzip.png "")  


## Datatype dependent slice operations


Spread operations are datatype specific when they operate on the actual data the spread holds. Most common examples:  

<span class="node">Sort (String)</span>  
<span class="node">Sift (String)</span>

<span class="node">Integral (Spreads)</span>  
<span class="node">Differential (Spreads)</span>  
