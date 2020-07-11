---
uid: 068e0370-b538-4d72-b9dd-98c4effdfeb3
---

# Freeframe Extended Specification
## Extending FreeFrame
>note:  
**Disclaimer:** The following extensions to the freeframe specification are not official. Based on the <a href="http://freeframe.sourceforge.net/spec.html" class="extURL" target="_blank">official freeframe system specification</a> they are a proposal how we could use spreaded inputs and outputs (i.e. lists of inputs and outputs). Naming is not so cool yet...  
  

Even though they are only proposals they are used with some of the [video tracking freeframe plugins](TODO INTERNALLINK:video-analysistracking) that ship with vvvv.  

# ad 3. Enumerated and derived types
**NumOutputs** (32-bit unsigned integer)  
Definition:  
Specifies the number of outputs that the plugin implements.  

- --  

**ParameterType** (32-bit unsigned integer)  
adding the following types:  

Value|Type|Description
--- | --- | ---  
20|valuespread|A spread/list/array of floats
21|colorspread|A spread/list/array of colors
22|stringspread|A spread/list/array of strings

# ad 4. Structures
**SetInputStruct** (size = 16 bytes)  
```
 SetInputStruct {
   DWORD Index;
   DWORD SliceCount;
   double* Spread;
 }
``` 
Fields:  
* Index: Index of the parameter to set.  
* SliceCount: Number of elements in the spread.  
* Spread: Pointer to the first slice (element) in the spread.  

- --  

**GetOutputStruct** (size = 8 bytes)  
```
 GetOutputStruct {
   DWORD SliceCount;
   float* Spread;
 }
``` 
Fields:  
* SliceCount: Number of elements in the spread.  
* Spread: Pointer to the first slice (element) in the spread.  

# ad 5. Functions
**Function Code Table**  
Global functions:  
adding the following functions  

Code|Function|Input value type|Output value type
--- | --- | --- | ---
20|getNumOutputs|none|NumOutputs
21|getOutputName|OutputNumber|Pointer to ParameterName
22|getOutputType|OutputNumber|ParameterType

Instance specific functions:  
adding the following functions  

Code|Function|Input value type|Output value type  
--- | --- | --- | ---  
20|getNumOutputs|none|NumOutputs
21|getOutputName|OutputNumber|Pointer to ParameterName
22|getOutputType|OutputNumber|ParameterType


# ad 5.1. Global functions
**getNumOutputs** (function code = 20)  
* Input value: none  
* Return value: NumOutputs indicating the number of outputs in plugin or FF_FAIL on error.  

**getOutputName** (function code = 21)  
* Input value: index: OutputNumber  
* Return value: 32-bit pointer to ParameterName (16 byte char array) containing the name of parameter specified by index. Returns FF_FAIL on error.  

**getParameterType** (function code = 22)  
* Input value: index: OutputNumber  
* Return value: ParameterType value which tells the host what kind of data the parameter index is. Returns FF_FAIL on error.  


# ad 5.2. Instance specific functions
**setThreadLock** (function code = 19, needs valid instanceID!)  
* Input value: doSet: boolean   
* Return value: Success/error code  

>note:  
This is useful for applications that use the DSFreeFrameWrapper that have the video running in a different thread than the video processing. you can set the threadlock before starting to set all parameters and remove it when finished. use the same threadlock in processFrameCopy before manipulating the image!  
  

**getOutputSliceCount** (function code = 23, needs valid instanceID!)  
* Input value: index: OutputNumber  
* Return value: Integer specifying the number of slices/elements in the spread  

**getOutput** (function code = 24, needs valid instanceID!)  
* Input value: index: OutputNumber  
* Return value: Pointer to float of first slice/element in spread  

**setInput** (function code = 30, needs valid instanceID!)  
* Input value: index: Pointer to InputStruct  
* Return value: Success/error code  
