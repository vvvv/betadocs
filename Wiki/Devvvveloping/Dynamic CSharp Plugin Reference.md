---
uid: 9fb98fc4-377b-49be-87ee-2c4741183b7c
---

# Dynamic C# Plugin Reference

## Cloning a Template

![](~/img/clone-d.png "")   

In order to create a dynamic c# plugin doubleclick in a patch to open the nodebrowser. Type "Template" to get a list of templates which you can choose to start from. Choose one of the templates prefixed with *d* and press *CTRL+Enter* or *CTRL+Click* to clone the template.   

In the dialog that now shows up choose a unique *Name* and *Category* for your node. Specifying a *Version* is optional, see [NodeAndPinNaming](xref:db8592a2-03c3-4e8c-a540-d11df5e83078).   

If the patch you're cloning in is not yet saved you'll also have to specify a path where to clone to. It is therefore always recommended to save the patch first because then the clone conveniently goes to a subdirectory of the patch.  

Press *Clone* to see your ready plugin appear in the patch. Rightclick the node to open the code-editor.   

Use the [Project Explorer](xref:721e9e4b-dec5-4786-878e-3efc4f09c5e7) to add/remove documents or references to a plugin.   


## PluginInfo

```csharp
[PluginInfo(Name = "Template",  
            Category = "Value",
            Help = "A Template",
            Tags = "simple, basic",
            Author = "vvvv group",
            AutoEvaluate = false)]
```


The PluginInfo attribute written above your plugin-class is used to describe a vvvv plugin.  

Inside the () brackets in the attribute statement there is a comma separated list of Name=Value pairs. Only the **Name** and **Category** ones are mandatory, all others are optional.   

Here is a [listing of all available PluginInfos](https://vvvv.org/pluginspecs/html/Properties_T_VVVV_PluginInterfaces_V2_PluginInfoAttribute.htm).  

Regarding the **AutoEvaluate** setting see the Evaluate() section below.  


## Defining Pins

```csharp
[Config("My Config Value")]  
public ISpread<double> FConfig;  

[Input("My Input String")]  
public ISpread<string> FInput;  

[Output("My Output Color")]  
public ISpread<RGBAColor> FOutput;  

```  
#### Attribute examples
```  
//specify a default value for a pin  
[Input("Input", DefaultValue = 255.0)]  

//specify a not spreadable pin.   
//The pin has only one slice   
//and the user can't change that.   
[.., IsSingle = true)]  

//specify the pins visibilty.   
[.., Visibility = PinVisibility.Hidden)]  

//specify a pin to be of type filename   
//to show a file-dialog on rightclick.  
[.., StringType = StringType.Filename)]  

```  

#### IDiffSpread example
```  
[Input("Write", IsBang=true)]  
IDiffSpread<bool> FDoWrite;  
...  
if (FDoWrite.IsChanged)  
...  

```  

#### Spread of Spread example
```  
//create a two-dimensional spread  
//exposed in vvvv with a data and  
//a bin-size pin.  
[..]  
ISpread<ISpread<double>> FInput;  

```  

#### PinGroup example
```  
//create a dynamic pingroup, where   
//the user can specify the pin count   
//via the Inspektor.   
[.., IsPinGroup = true)]  
ISpread<ISpread<double>> FInput;  

```  


A Pin is being defined by 2 lines of code:  
* a PinInfo attribute (Config, Input or Output)  
* a variable declaration  

#### PinInfo attribute
The PinInfo attribute is used to describe a pin. The attribute immediately precedes the declaration of an input or output variable.  

Inside the () brackets in the attribute statement the first string argument is mandatory and specifies the pin's name. A further comma separated list of Name=Value pairs (that is optional) allows you to describe a subtype of the pins value by setting a Default-, Min-, MaxValue and more.  

Here is a [listing of all available PinInfos](https://vvvv.org/pluginspecs/html/Properties_T_VVVV_PluginInterfaces_V2_IOAttribute.htm).  

#### Variable declarations
In most scenarios you'll want to declare your in- and outputs of the generic type ISpread<T> where for T you can specify any type like:  
**float, double, bool, int, ..** -  value pin  
**string** -  string pin  
**RGBAColor** -  color pin  

If you want to ask from an input if it has changed then simply use IDiffSpread<T> instead of ISpread<T> in the declaration and call .IsChanged whenever you need to know.  

#### Spread of Spread
If you declare a variable as ISpread<ISpread<T>> then next to the actual pin (that holds the data) you get a free BinSize pin that allows you to specify how that data is structured into bins.   

If you still want to know if the input was changed, only the outer spread should be declared as IDiffSpread<T>.  

Alternatively you can also make this pin a PinGroup where instead of the BinSize pin you get a free PinCount config pin, see example to the left.   

#### Add/Remove pins
There are 2 ways to do this at runtime:  
* simple: use a PinGroup: This only works in combination with an ISpread<ISpread<T>> with any T (see codesnipped on the left).   
* flexible: have a look at the code of the Template (Value DynamicPins).  

#### Connection callbacks
In the unlikely case that you need to react to pin connect/disconnect events use Pin<T> instead of ISpread<T>, see [Pin(T) Events](https://vvvv.org/pluginspecs/html/Events_T_VVVV_PluginInterfaces_V2_Pin_1.htm).  



## Evaluate

```csharp
public void Evaluate(int SpreadMax)  
{   
  FOutput.SliceCount = SpreadMax;

  for (int i = 0; i < SpreadMax; i++)
    FOutput[i] = FInput[i] * 2;
}  

```  

This is the heart of your plugin. The Evaluate() function is run once every frame if:  
* something is connected downstream  
* or you have set AutoEvaluate=true (see PluginInfo above)  

Here you do the main calculation of your plugin. If you're looking for a section to initialize some parts of your code (ie. run them only once), see the next section (Constructor).  

As an input parameter the function hands you the *SpreadMax* which is the maximum slicecount of all connected spreads on all inputs of the plugin. You will typically use this to set the slicecount of your output pins as shown in the code to the left.  

Please note: if ANY of your input pins is an ISpread<ISpread<...>>, you should evaluate SpreadMax yourself as you can see below. Like this a 2d-spread will only contribute to the spreadmax with its "bin count" which is what you typically want.  


```   
SpreadMax = SpreadUtils.SpreadMax(FInput1, FInput2 /* state ALL your inputs here*/);   

```   

## The Constructor: Initializing stuff

```csharp
public MyNodeClassname()  
{   
  //initialize stuff
}  

```  

```  
public class MyNodeClassname:   
IPluginEvaluate,   
IPartImportsSatisfiedNotification  
{  
...  

public void OnImportsSatisfied()  
{  
  //access your in-/outputs here
}  

```  

You'll use a constructor if you have parts of your code that only need to run once. Note that a constructor is optional and therefore most of the templates come without one.   

If you need to access any of the variables you defined as in- or outputs you'll have to take extra care and implement IPartImportsSatisfiedNotification as shown in the example to the left. For an actual usecase see the code of Template (Raw).  



## The Destructor: Disposing stuff

```csharp
public class MyNodeClassname:   
IPluginEvaluate,   
IDisposable  
{  
...  
//called when the plugin gets   
//deleted  
public void Dispose()  
{  
  //unsubscribe from events
  //and call dispose on resources
  //your plugin has created.
}  

```  

In case your plugin makes use of resources which need to be released when the plugin gets deleted you need to implement the <a href="http://msdn.microsoft.com/en-us/library/system.idisposable%28v=vs.110%29.aspx" class="extURL" target="_blank">IDisposable</a> interface. In its Dispose method you can do all the necessary clean-up tasks.  


## Accessing Internals: The HDEHost

```csharp
[Import()]  
public IPluginHost2 FPluginHost;  

[Import()]  
public IHDEHost FHDEHost;  

```  

There are two entry points if you want to access some of the internals of vvvv:  
* want to get/set information on the plugin you're working at, have a look at: [IPluginHost2](https://vvvv.org/pluginspecs/html/AllMembers_T_VVVV_PluginInterfaces_V2_IPluginHost2.htm)  
* want access to the whole of vvvv, have a look at [IHDEHost](https://vvvv.org/pluginspecs/html/AllMembers_T_VVVV_PluginInterfaces_V2_IHDEHost.htm)  


## Usings

```csharp 
using System;  
..  
using VVVV.PluginInterfaces.V2;
```  

All entities in .NET can be reached via a global path, which is a combination of the namespace in which the entity is defined and the name of the entity. So e.g. VVVV.PluginInterfaces.V2.ISpread<bool> is the full path to the type ISpread<bool> which is defined in the namespace VVVV.PluginInterfaces.V2.  

The using statements are there to be able to shorten your code by only saying ISpread<bool>. For that to work it is necessary to use the namespace (VVVV.PluginInterfaces.V2) once at the beginning of the code.  


## Debugging

```csharp
[Import()]  
public ILogger Flogger;  
...  

Flogger.Log(LogType.Debug, "foo");  

```  

The most basic way of debugging parts of your code is writing out log-messages that you can view in <span class="node">Renderer (TTY)</span>. You can do so by importing the ILogger and calling .Log() on it as shown in the example to the left.   

#### Breakpoints
If you want to set breakpoints and step through your code line by line you'll need an IDE like SharpDevelop or VisualStudio and do the following:  
* load the .csproj of your plugin   
* set a breakpoint in your code  
* attach the IDE to the running instance of vvvv.   
Now when a breakpoint is hit the IDE stops vvvv and you can step through your lines of code.  


## Further optional interfaces to implement




* IBackgroundColor allows a GUI plugin to specify the background color for the window it is hosted in (mostly to prevent flickering when the window goes fullscreen).  
* [IQueryDelete](https://vvvv.org/pluginspecs/html/AllMembers_T_VVVV_PluginInterfaces_V2_IQueryDelete.htm) provides a plugin with the possibility to prohibit its own deletion.   
* [IMainLoop](https://vvvv.org/pluginspecs/html/AllMembers_T_VVVV_PluginInterfaces_V2_IMainLoop.htm) allows to subscribe to mainloop events.   
* [IDXDeviceService](https://vvvv.org/pluginspecs/html/AllMembers_T_VVVV_PluginInterfaces_V2_EX9_IDXDeviceService.htm) provides access to Direct3D9 devices created by vvvv.   
* [IStartable](https://vvvv.org/pluginspecs/html/AllMembers_T_VVVV_PluginInterfaces_V2_IStartable.htm) allows some code to be executed on startup.   





