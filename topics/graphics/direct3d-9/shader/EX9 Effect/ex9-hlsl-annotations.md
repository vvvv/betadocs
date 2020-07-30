---
uid: c1f1412a-9d7c-48d0-911a-bea5d78ca373
---

# EX9 HLSL Annotations
Following Annotations for parameters in Effect-Files are currently supported in vvvv. All Annotations are case-insensitive.  

**annotation** |**description** |**type**  
--- | --- | ---  
uiname   |defines the name for the pin of the effect node representing this parameter. if you don't declare a parameter with the annotation "uiname", the pin will be given the name of the parameter. |string    
--- | --- | ---  
uimin  |define the minimum for this scalar-type parameter; value may not be smaller than defined (supported by gui) ***** |float or int  
--- | --- | ---  
uimax   |define the maximum for this scalar-type parameter; value may not be taller than defined (supported by gui) ***** |float or int  

***** works only for scalar types (ValueTypes): int and float  

### Example
```hlsl  
float foo;
```  
results in a value pin called <span class="pin">MyParamter</span> on the effect node with a subtype defaulting to 0 and a range of MinFloat to MaxFloat.  

```hlsl  
float foo <string uiname = "My Parameter"; float uimin = 0; float uimax = 1;> = 0.5;
```  
results in a value pin called <span class="pin">My Parameter</span> on the effect node with a subtype defaulting to 0.5 and a range of 0 to 1.  