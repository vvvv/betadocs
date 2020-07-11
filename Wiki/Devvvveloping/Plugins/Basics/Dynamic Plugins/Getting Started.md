---
uid: 0e08269e-26d9-414d-bd0c-e608d8b1884c
---

# Getting Started
For *patching* a new node you would use CTRL-SHIFT-P to place a fresh empty patch inside your current patch, start placing some ioboxes for inputs and outputs, name them and connect them to nodes doing the actual work inside your subpatch / module.  

For *writing* a new node there is no shortcut for starting an empty c# plugin. We thought it might be easier to start from very simple templates which already have an input and an output.   

### How?
So instead of creating an empty text file, you start by selecting some template like <span class="node">Template (Value)</span>. After creating that template you will see that it already works and multiplies the Input by 2. A right click shows the inside (just like a right click on a subpatch node shows that patch). Note that you can't modify a template. So what you need to do is to clone the template. To clone a template double left-click on a patch as you would do to create a node normally, type "tem" and finally select the template to be cloned while pressing CTRL.  
In the dialog choose a new name.   
You can at any time choose a new name, category or version by cloning your own node. This is the most convenient way of doing the rename in a consistent way. Under the hood several entities like files, folders, classes and infos are renamed, so just use that feature and don't be afraid of giving stupid names since you always have a one-click tool to fix that...  

Last thing you need is a small idea. For the beginning think in terms of values, colors or strings. A small node that does some simple logic that would take up to 5 nodes to patch.  

Connect ioboxes to in- and outputs to instantly see how the outputs change after changing and saving the .cs file (CTRL-S from within the code editor). Save your test patch within your project directory which is in *vvvv*\plugins\*YourDynamicPlugin* and name it "*YourDynamicPlugin* (*Category* *Version*) help.v4p".  

## The Editor
### regions
The code editor supports code folding. This just means that you can hide/show certain regions of your code by clicking the -/+ buttons at the left of your code.  
regions are marked with   
```  
# region SOMEREGION
# endregion SOMEREGION
```
where SOMEREGION stands for any region name (which can include spaces).  
The template comes with regions "usings", "PluginInfo" and "fields & pins".   

### colors
The code editor automatically uses certain colors and type styles to make the code more readable. In general you can say that the type of token decides on what color or type style is used.   
After some time you will benefit from that instant feedback, since it shows you if the code is well formatted.  

## Understanding the Template (Value)

The first language feature of c# you are confronted with is that of namespaces. Namespaces are just a way to structure the huge collection of libraries that come with .NET and some additional that come with vvvv.  
You don't need to know all these libraries, you only need to know the concept.   
Compare that to all animals and how they are classified. You also don't need to know all animals to get the idea... <a href="http://en.wikipedia.org/wiki/Biological_classification" class="extURL" target="_blank">bio classification</a>   

You also can think of it as a general hierarchical structure:  
```  
Vehicle.Car.VW.Polo
```  
It goes from unspecific to specific and the dots mark the subfolders.  

### usings 
All entities in .NET can be reached by a global path, which is a combination of the namespace in which the entity is defined and the name of the entity.  

```  
VVVV.PluginInterfaces.V2.ISpread<bool>
```  
VVVV.PluginInterfaces.V2 is the namespace where ISpread<bool> (a spread of booleans) is defined.  

The using statements are there to be able to shorten your code by only saying ISpread<bool>. For that to work it is necessary to *use* the namespace (VVVV.PluginInterfaces.V2) once at the beginning of the code.  
For now note that just a few standard namespaces are *used* from which 2 are standard .NET namespaces:  
```  
using System;  
using System.ComponentModel.Composition;
```  
and 5 vvvv namespaces  
```  
using VVVV.PluginInterfaces.V1;  
using VVVV.PluginInterfaces.V2;  
using VVVV.Utils.VColor;  
using VVVV.Utils.VMath;  
using VVVV.Core.Logging;
```  

here are some more for your future experiments: [namespaces](TODO INTERNALLINK:namespaces).  

### namespace
Also your new node is such an entity defined in a namespace. Since it is a node it is cool to keep the name of the namespace "VVVV.Nodes".  
```  
namespace VVVV.Nodes  
{  
}
```  

#### code blocks
It is totally fine to accept and ignore all those namespace stuff for now and keep going.  

Just note that those brackets {} mark a code block and also note that all the rest of the file is within the code block of the *VVVV.Nodes* namespace.   

Code blocks in general are needed to structure your code and it is very common that code blocks are nested. Therefore it is perceived as good style to indent the inlying code using TABs to make this nested structure more visible to humans (who typically don't track {} brackets).  

### PluginInfo 
```  
[PluginInfo(Name = "Template",  
	    Category = "Value",
	    Help = "Basic template with one value in/out",
	    Tags = "")]
```
The plugin info is part of the declaration of your node. It states that the class defined below is a node. Only classes that are marked by such a PluginInfo signature will get listet in the node browser.  
>note:  
Name and Category are mandatory while the rest is optional.  
  

See more [PluginInfo Attributes](TODO INTERNALLINK:PluginInfo Attributes)  

### the class
A node is a class and a class is a very basic building block in c#. It just makes some brackets around data and code. You need that for writing nodes.   
>note:  
Compare this to a patch:  
Inlets and outlets (named ioboxes) in modules correspond to the data part and the nodes within correspond to the code which says what to do.  
  

### fields and pins
The data part: mostly inputs and outputs of your node.  
```  
[Input("Input", DefaultValue = 1.0)]  
ISpread<double> FInput;
```  
Like in the declaration of the whole node, again we have both   
* the raw c# notation (in this case a data field)  
* and above some signature to tell vvvv that this data should appear as a pin.  

Note that fields without pin signature can make perfect sense. It is then a private piece of data, which you need for your calculations but don't want to show the user of your node as a pin.   
When you change your mind and want to make something configurable by the user you would place an inputpin signature above and will get a pin to receive data from the user.  
Or you might want to show some precalculations to the user. For this you would add an output pin signature above the data field and the node will get another output pin.  
```  
[Output("Step 2 in big Calculation")]
```  
>note:  
You can again compare the adding of a pin signature with naming an iobox in a module, which also results in a new pin in the patchs' node representation. In both cases the patch or the c# node are already working and adding the signature or naming the iobox only result in adding the pin.  
  
For a pin signature it is mandatory to specify if it should be an input or an output and the Name. All further attributes are optional.  

How to configure pins: [Pin Attributes](TODO INTERNALLINK:Pin Attributes)  

#### Pin Type: ISpread<T>
```  
ISpread<double> FInput;  
ISpread<double> FOutput;
```  
Above you see the raw c# declarations of input and output in the Template.  
To the left there is the **type** of the pin data (ISpread<double>), on the right the internal c# name (FInput, FOutput), which typically starts with "F" for "field".   
The declaration follows the scheme *FieldType FieldName;*  

Note that in our example the type of data for input and output is the same: just a spread of doubles (ISpread<double>). A double is a floating point number (informatic term), which is a real number (mathematic term), which is just a number (for all). See other templates how to work with other spreads (like a spread of strings).  
In general we say that **all inputs and outputs are of type ISpread<*T*>** where *T* stands for the element type which can be:  
**float, double, bool, int, ..** - resulting in a value pin  
**string** -  string pin  
**RGBAColor** -  color pin  
and so on  

Only fields of type ISpread<*T*> (with any *T*) can be turned into pins by adding a pin signature.  

#### Other fields
```  
[Import()]  
ILogger Flogger;
```  
ILogger is some interface on which you can call the method Log(). A method is something that does something, in this case writing into a <span class="node">Renderer (TTY)</span>. So the Flogger can easily be used to write out some debug information.  

### the Evaluate method
We just learned that a c# method does something.   
Well, didn't we also want to get our node to do something?   
```  
public void Evaluate(int SpreadMax)  
{  
}
```  
declares a new method.  

You can declare several methods in your class.  
The **Evaluate** method however again is a special vvvv thing. It is called when the output values are needed.  
They are needed when   
* the evaluation of the whole patch system requires the output of your node to be computed or  
* you hover with mouse over an output (resulting in a tooltip with the current value) or   
* if an IOBox is attached and therefore the output values are needed to update the GUI.  
You can see that your node is evaluating only when the output is needed by following these steps:  
* create a <span class="node">Renderer (TTY)</span>  
* ensure that nothing is linked to the outputs of you node  
* hover with the mouse over an output  
You should now see that the node is only doing what it is told to, when the output is needed: the output is needed because of the tooltip, therefore Evaluate is called, which also results in prompting messages to the <span class="node">Renderer (TTY)</span> (explained below). Hovering away stops the logging and therefore shows that Evaluate is not called anylonger.  

If you want to ensure that the node is just called each frame (independently of if any ouput value is needed) you would need to add an attribute to the PluginInfo:  
```  
[PluginInfo(...,  
	    AutoEvaluate = true)]
```

>note:  
Again you can compare the Evaluate method with the nodes within a module: both work on the input data and are responsible for feeding the outputs.  
So everything that you want your node to do comes into the evaluate method between those brackets.  

```  
FOutput.SliceCount = SpreadMax;
```  
says that the size of the output spread should be equal to the biggest spread of all inputs, and since for now we only have one input, output and input spreads will have the same slicecount.  
```  
for (int i = 0; i < SpreadMax; i++)  
    FOutput[i] = FInput[i] * 2;
```
For each slice calculate the output by multiplying the input slice by 2.  
Note that you could do more in the for loop. For that however you would again need a code block:  
```  
for (int i = 0; i < SpreadMax; i++)  
{  
    someCommand;
    otherCommand;
}
```  

- --  

```  
Flogger.Log(LogType.Debug, "Logging to Renderer (TTY)");
```  
writes some debugging message to the console.   
Typically you would use the logging feature to test if some code has been executed (e.g. inside an if statement).   

