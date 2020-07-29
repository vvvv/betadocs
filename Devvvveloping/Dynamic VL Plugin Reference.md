---
uid: 2879ae37-9e84-42ee-8e2e-8444d274bb6b
---

# Cloning a Template

![](~/img/clone_v.png "")   

![](~/img/DynamicVLRef_CloneNodeDialog4.png "")   



In order to create a dynamic VL plugin doubleclick in a patch to open the nodebrowser. Type "Template" to get a list of templates which you can choose to start from.   

Choose one of the templates prefixed with *v* and press <kbd>CTRL+Enter</kbd> or <kbd>CTRL</kbd>+Click on it to clone it. The two options you have is:  
* Template (Value)  
* Template (Value Stateless)  

Where *stateless* means that your plugin does not store a state, ie. it is not saving values for re-use in the next frame. This choice is only offered here to save you some clicks later. You can still change your mind at any time in the VL editor.  

In the "Clone Node" dialog that now shows up choose a unique *Name* and a *Category* for your node. Specifying a *Version* is optional, see [NodeAndPinNaming](xref:db8592a2-03c3-4e8c-a540-d11df5e83078).   

If the vvvv patch in which you're cloning in is not yet saved you'll also have to specify a path where to clone the VL template to. It is therefore always recommended to save the vvvv patch first because then the clone conveniently goes to a subdirectory "\vl" next to the vvvv patch.  

Press *Clone* to see your plugin appear in the patch. Rightclick the node to open the VL editor.   


# Defining Pins

![](~/img/DynamicVLRef_NewInput2.png "")  
*VL editor. Adding a new Input.*  
![](~/img/DynamicVLRef_MyNode.png "")  
*VL editor and the node in vvvv.*  



There are two ways to create input and output pins in VL:  
* via the NodeBrowser by typing a pin's name and hitting either *Input* or *Output* to place a pin in the patch.   
* after having started a link by doubleclicking to finish a link with a pin  
You can always rename a pin by doubleclicking its label. For input pins you can set a default by pressing the middle mousebutton on it or selecting *Configure* via the rightclick-contextmenu.  

Initially a pin has no type specified and it will automatically infer its type from the pin it is connected to. This can be convenient but it is also good practice to annotate a pin with a specific type. To do so middleclick a pin to open the TypeBrowser and enter the name of a type. The following is a list of most commonly used types:  
* Boolean  
* Float32  
* Integer32  
* RGBA  
* String  
* Vector2, Vector3, Vector4, Matrix  
* MouseDevice, KeyboardDevice, TouchDevice  

For a pin defined like this, VL will always only see a single value, even if a spread is connected in vvvv. See [Think slice-wise](xref:2879ae37-9e84-42ee-8e2e-8444d274bb6b#think-slice-wise) below.  



![](~/img/DynamicVLRef_Spread_0.png "")   
*An Input pin specified as Spread<T>.*   



#### Spread of Spreads

In order to work with a spread of data inside a plugin you need to specify the type of the pin to be of *Spread<T>*, eg:  
* Spread<Boolean>  
* Spread<Integer32>  
* ...  

For each input pin annotated with *Spread<T>* a corresponding *Bin Size* pin is created on the node in vvvv that allows you to specify how its data is structured into bins for vl. VL will always only see one of those bins at a time. See *Think slice-wise* below.  

Note that you may encounter situations where you will rather not want such a *Bin Size* pin but at the moment there is no way to get rid of them! We have planned this for a later update  



# Update



The *Update* operation is the heart of your plugin. It is called every frame. Here you do the main calculation of your plugin. If you're looking for a section to initialize some parts of your code (ie. run them only once), see the next section (*Create*).  



![](~/img/DynamicVLRef_ThinkingSlise-wise2_0.png "")   




#### Think slice-wise
The *Update* operation is called once per frame. If any of your plugins inputs is receiving a spread from vvvv, *Update* is called multiple times: Once with the first slices of all inputs, then with the second slices of all inputs,...   

This is important to understand as it is different to when you create patch in vvvv: When patching in VL you only think about a single slice even though the operation may then be executed for multiple slices consecutively, but you don't have to worry about that!  



![](~/img/DynamicVLRef_BinSizes2.png "")   




- --  

If you annotate the type of an input to be of: Spread<T> then your plugin is operating on *bins* instead of *slices*. So in this case with every call of *Update* VL receives a bin (ie. subset of the incoming spread). Still you don't have to worry about multiple consecutive bins, only think about operating on one bin. The calling of your operation for multiple consecutive bins happens automagically.  


# Create: Initializing Stuff



You'll use a constructor if you have parts of your code that only need to run once. Note that a constructor is optional and therefore the template doesn't show its usage.  



![](~/img/DynamicVLRef_PinToConstructor.png "")  
*Selecting and assigning a pin to Create.*  


#### Nodes, Pins and Links
You can place any nodes, pins or links on the *Create* operation by selecting them and choosing: *Assign -> Create* in the right-click context-menu.   



![](~/img/DynamicVLRef_LinkToConstructor.png "")  
*Selecting and assigning a link to Create.*  



#### Pads and IOBoxes
Pads and IOBoxes are always un-assigned in that they don't belong to any single operation but can be connected to/from any operation.  

So in order to initialize a Pad with a constant value in the constructor you simply **assign the link** that goes from IOBox to Pad to *Create*.  


# Dependencies

![](~/img/DynamicVLRef_Dependencies.png "")  
*Adding a reference to another VL document.*   


By default each VL document depends on the *VL.CoreLib.vl* package, which gives you access to the VL Core library nodes.   

You can add dependencies to other packages or VL documents via the document-menu: Dependencies   

You'll then have access to all nodes that are defined in the referenced package or document.  


# Debugging

![](~/img/DynamicVLRef_Debugging2_0.png "")  
*Inspecting a value in an IOBox and on a link.*   


In order to inspect the value of a pin simply hover it with the mouse or start a link from it and then middleclick to create an IOBox that will always show you the pins current value.   



# Project Structure

![](~/img/DynamicVLRef_DocumentPatch3.png "")  

*The Document Patch <kbd>Alt+P</kbd>.*  


Typically a simple plugin will consist of a single VL document with multiple patches and references only to the default dependencies (like the  VL.CoreLib package).  

You can get an overview of all elements in your document by viewing the *Document Patch* which you can always reach via <kbd>ALT+P</kbd>. It shows you all Classes, Records, Operations and Utility Patches the document holds.  

Still from that simple structure you can expose multiple nodes to vvvv. You can have any vl datatype or operation show up as a node in vvvv.   



![](~/img/DynamicVLRef_OperationAsVVVVNode2.png "")   
*Generic indicator is turned off for this operation.*  


### Exposing Operations
In order to have a vl operation show up as a node in vvvv it needs to meet two criteria:  
* the category of the group it is defined in needs to start with *VVVV*  
* it needs to be non-generic (see below)  



![](~/img/DynamicVLRef_DocumentPatch_ClassExposedToVVVV3.png "")   
*A non-generic class is exposed to vvvv.*  


### Exposing Datatypes
In order to have a vl datatype show up as a node in vvvv it needs to meet the following criteria:  
* it needs to be a Process  
* its category needs to start with *VVVV*  
* it needs to be non-generic (see below)  




- --  
To make sure an operation or datatype is ***non-generic*** uncheck its Generic indicator. In case all pins already have a type inferred now all is fine, otherwise certain pins may show an error indicating that they need a type annotation.  



# Fine Print


### Subtypes
While in c#-plugins you can define subtypes (eg. min, max, default, stepsize,... for values) for any input or output pin, the only thing you can specify for inputs in vl-plugins is a default (see *Defining Pins* above).  

### Configuration Pins
While in c#-plugins you can create configuration pins (ones that only show up in the inspektor), as of now there is no way to do this with vl-plugins.  

### Pin Groups
While in c#-plugins you can define a spread to show up as *Pin Group* instead, ie. many side-by-side pins whose count can be set via the Inspektor (see +, Cons, ... nodes) this is not possible yet for pins in vl-plugins.  

### Boygrouping
As with any other effect or plugin, vl-plugins cannot easily be boygrouped. The two options you have is:   
- copy the vl-plugin manually to the clients  
- reference the vl-plugin from a shared network location that both server and clients can access  





>note:  
More about VL: <a href="https://www.gitbook.com/book/vvvv/the-gray-book" class="extURL" target="_blank">The Gray Book</a> specifically the chapter: <a href="https://vvvv.gitbooks.io/the-gray-book/content/en/VL_for_vvvv_users/VL_for_vvvv_users.html" class="extURL" target="_blank">VL for vvvv users</a> for a start.