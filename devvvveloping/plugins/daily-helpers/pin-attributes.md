---
uid: 8d9059b9-e075-4b42-91ef-7599f6879028
---

# Pin Attributes
Pin Attributes describe the appearance of a data field in vvvv.  

Most important is if it is an input or output.  

``` 
[Input("Input", DefaultValue = 1.0)]  
ISpread<double> FInput;  

[Output("Output")]  
ISpread<double> FOutput;  
```

In between the () brackets a comma seperated list of pin attributes can be set like that:  
**PinAttribute = PinValue,**  

The value you specify has to be of the pin attributes' type.  

All available properties are listed under: [/pluginspecs/html/AllMembers_T_VVVV_PluginInterfaces_V2_PinAttribute.htm](https://vvvv.org/pluginspecs/html/AllMembers_T_VVVV_PluginInterfaces_V2_PinAttribute.htm)  

## examples:
Specify a default value for a pin. This is also the value used on <span class="keyseq"><kbd>ALT</kbd></span>+rightclick (reset pin to default).  
```  
DefaultValue = 255.0  
```

Specify a not spreadable pin. The pin has only one slice and the user can't change that.   
```  
IsSingle = true  
```

Specify the pins visibilty.   
```  
Visibility = PinVisibility.Hidden  
```

Speficy a pin to be of type filename to show file-dialog on rightclick.  
```  
StringType = StringType.Filename  
```
Creates a dynamic pingroup, where the user can specify the pin count via Inspektor. This will only work in combination with a ISpread<ISpread<*T*>> with any *T*.  
```  
[Input("Input", IsPinGroup = true)]  
ISpread<ISpread<double>> FInput;  
```