---
uid: 10b82e0c-720a-48e1-91e4-d8c65d2c3be1
---

# Patching Basics

# Introduction
Programming with vvvv is commonly referred to as ***patching***.   
The editors canvas is called the ***Patch***.   
The building blocks that make your programs are called ***Nodes***.   
Nodes have input and output parameters called ***Pins*** which are connected by ***Links***.   

The following reference goes into details about those 4 main components.  

# Patch


### Opening a patch
To open a patch middle-click in the Patch Editor to open the Main Menu and choose:   
* Open (CTRL+O)  
* Open in Patch (CTRL+SHIFT+O)  

### Saving a patch
To save a patch middle-click in the Patch Editor to open the Main Menu and choose:   
* Save (CTRL+S)  
* Save As... (CTRL+SHIFT+S)  
Everytime you save a patch its previous version is backed up under the same filename but ending in ~.xml. So if ever you need to go back to that previous version just rename it to .v4p and you can open it again.   



![](~/img/patchingBasics_mouse4.png "")   

### Using the mouse
When patching always remember:  

* **Changing the position** of a node or a window is done intuitively using a **left button drag**  
* If you want to **change any values** of a pin (or in an IOBox) you will do it with a **right button drag**  
* You can always emulate a **middle mouseclick** with a **SPACE + rightlick** in case you don't have a middle mousebutton  




### Hiding vs. Closing a patch
* If you **Close** a patch (CTRL+W), the patch will be **removed from the system**. The node containing this patch is deleted.  

* If you **Hide** a patch (ALT+3), the patch will still be **part of the system** and **continue working**. Only it is no longer visible.   

See also: [Window Modes](xref:5aa4e8e0-fc2c-4112-a985-7f4f0208bf48).  



![](~/img/BasicPatching_Locking2.png "")   

### Locking a patch

To lock a patch press CTRL+E. A locked shows a '#' symbol in its topleft corner.   

In a locked patch:  
* all nodes still work   
* it is still possible to change values of the visible IOBoxes  
* nodes can no longer be moved  
* [hidden nodes](xref:10b82e0c-720a-48e1-91e4-d8c65d2c3be1#hiding nodes) and links are invisible  

To unlock, use CTRL+E again.  




### Scrolling
You can scroll in a patch by **right clicking on an empty space** and start **dragging**.   

Alternatively or while making a [link](xref:10b82e0c-720a-48e1-91e4-d8c65d2c3be1#link) you can:  
* use the mousewheel to scroll vertically  
* press ALT while using the wheel to scroll horizontally  
* press CTRL in addition to speed up scrolling  



![](~/img/BasicPatching_Comments2.png "")   

### Comments
Double click with the left button to bring up the [Node Browser](xref:eeb8526d-0085-4219-a138-32ac397853f1). Then enter the text you want to have as a comment in the patch. Make sure the text is not matching any node before pressing ENTER to create a comment.   

A comment is essentially an <span class="node">IOBox (String)</span> with its input and output pins hidden. So you can always just doubleclick to change it.   




### Making a Module
If you want to make a patch into a reusable module, see:  
* [Modules](xref:b66f153a-f7c3-4867-a8c9-bce69861d759#modules)  
* [SubPatches](xref:b66f153a-f7c3-4867-a8c9-bce69861d759)  


# Node

![](~/img/BasicPatching_NodeCategory3.png "")   


Nodes are the building blocks of your patches and each represents a specific functionality. A nodes identifier is structured in the form:  
 Name (Category Version)
The combination of name, category and version is unique for each node in vvvv. Versions are optional an can be any number of space-separated strings.  

While in a patch you always only see the nodes name. Hover a node to see its full identifier in the tooltip.  



![](~/img/BasicPatching_NodeIcons5.png "")   


### Icons
Nodes can have different icons:  
* has vvvv nodes  
* has VL nodes  
* has code (hlsl or c# code editor)  
* has a renderer/window  

**Every node with an icon** can be rightclicked to show its editor or window. Nodes without an icon are built-in native nodes and can not be manipulated.  

To get an overview of all the pins of a node, select it and press CTRL+I to open the [Inspektor](xref:9666611a-6f15-4b33-8300-69f56d9ec7d4).  

To find out more about a nodes functionality, select it and press F1 to open its helppatch.  



![](~/img/BasicPatching_NodeBrowser.png "")   


### Adding nodes to a patch
You can browse a list of available nodes by **double-clicking anywhere in a patch** to pop up the [Node Browser](xref:eeb8526d-0085-4219-a138-32ac397853f1).   

There you can start typing tags (separated by space) to search for a node with specific functionality or you can get to a category-sorted view by rightclicking in its text-area.   

When you found a node you want to use in your patch press enter or select it with a left click and see it inserted in the patch.  

### Deleting nodes
Select a node and press the Delete or BackSpace keys to remove it from the patch.   

### Moving a selection of nodes
Press the cursor keys to move them by 1px.  
Press SHIFT and the cursor keys to move them by 10px.  



![](~/img/BasicPatching_GroupingNodes3.png "")   

### Grouping nodes
Select a group of nodes and press CTRL+G to replace them with a [SubPatches](xref:b66f153a-f7c3-4867-a8c9-bce69861d759) of the same functionality and keeping their connections to other nodes.   

Note that the created subpatch still needs to be saved. Therefore it is good practice to rightclick the new node immediately and press CTRL+SHIFT+S to save it under a specific name.   




### Hiding nodes
Press CTRL+H to mark a selection of nodes/links as hidden.  

Hidden nodes/links are not visible or accessible anymore when a patch is [locked](xref:10b82e0c-720a-48e1-91e4-d8c65d2c3be1#locking-a-patch). In an unlocked patch they will stand out with a lighter shade of grey.  



![](~/img/BasicPatching_ColorOfTheNodes4.png "")   


### Colors of nodes
* **Red**: the node has a problem, see [Red Nodes](xref:36621302-10e7-47fe-a8d0-b609c758974d#red-nodes)  
* **Pink**: same as red, only the node is also marked as hidden  
* **Blue**: the node is [boygrouped](xref:9d029794-1266-4e60-961f-33e6f95af7e6)  
* **Light blue**: same as blue, only the node is also marked as hidden  
* **Light blue & Grey border**: the [SubPatches](xref:b66f153a-f7c3-4867-a8c9-bce69861d759) contains some Boygrouped nodes  

### More
* Align a selction of nodes by pressing CTRL+L  
* Reset all of a nodes inputs to their defaults: ALT+Rightclick on the node  


# Pin

![](~/img/BasicPatching_PinTypes3.png "")   


On its top and bottom a node can have any number of inputs and outputs, called pins.   

* **Inputs** are where you specify the parameters feeding the functionality of the node  
* **Outputs** are the results of the nodes function.   
* **Configuration pins** are only visible via the [Inspektor](xref:9666611a-6f15-4b33-8300-69f56d9ec7d4) and are used to define parameters of a node that are not supposed to change at runtime.   




### Data Types
Every pin in vvvv is of a specific type of data.   
The most common of those types are:  

**Primitive**  
* Value (numeric values: boolean, integer or double)  
* String (text)  
* Color  
* Enumeration (ordered listing of items)  
**Non-Primitive**  
* Node (collective name for all other datatypes, like: Texture, Transformation, Mesh,...)  

You can introduce your own custom data-types using [plugin](xref:766d8ac2-5145-417d-b2df-37d24e3b2b6f).  



![](~/img/BasicPatching_Subtype.png "")   

### Subtypes
All primitive datatypes can have subtypes which more precisely specify a value-range a pin is looking for. Examples  
* a number subtype specifies: whole number (integer) in the range of 1 to 10  
* a text subtype specifies: a filename  

Subtypes are only used for the user interface to offer more suitable means for entering the desired data to a pin but they do not influence the calculation a node is doing.   



![](~/img/BasicPatching_ChangingPinsValue.png "")   

### Inspecting a pin's value
Move the mouse over any pin to see a tool tip showing its name and current value.  

### Changing a pin's value
Values of inputs that have one of the primitive data types can be changed directly on the pin. Changing the value of a pin is like editing an IOBox:  

* **Value pins**: Right-drag on the pin vertically to change its value. See [Value IBOxes](xref:86693dba-d049-4027-874d-d53f0437ad66#value).  

* **Color pins**: Right-drag on the pin to change its color. See [Color IOBoxes](xref:86693dba-d049-4027-874d-d53f0437ad66#color).  

* **String pins**: Right click the pin to invoke the operation according to its subtype. See [String IOBoxes](xref:86693dba-d049-4027-874d-d53f0437ad66#string).  

* **Enumeration pins**: Right click to invoke the pull-down menu with all possible values. See [Enumeration IOBoxes](xref:86693dba-d049-4027-874d-d53f0437ad66#enumeration).  

### Resetting a pin's value
* Alt+Rightclick an unconnected pin to reset it to its default.  
* Alt+Rightclick a node to reset all of its unconnected pins to their defaults.  


# Link

![](~/img/BasicPatching_Links1.png "")   



### Connecting pins
Two pins that have the same data type can be connected by a link.   

1. Do a left click on one of the pins you want to connect (input or output) 
1. You will see a link following the mouse cursor. All pins you can now connect to will grow to larger gray squares (Note: Hidden pins will not show up but can be connected as well). 
1. Do a left-click on the second pin. Your connection is made.

* To cancel a link while making it, simply do a right click.  




**Every input pin can only take one link!**   
Therefore, when you try to add another link to an input that already has a link, the existing link will be replaced by the new link.   

**Outputs can have any number of links going from them.** Except for the rare *Video*, *Audio* and *Midi* outputs of nodes in the *DShow9* category that also can only handle one link!  

To create multiple links from the same output pin, start with a right click on it and then simply left-click on all input pins you want to connect to.  

While making a link you can middle click somewhere to create an IOBox that will contain the data that's in the pin you're coming from. Middle click that IOBox once again to automagically give it the name of a this pin. See also: [Descriptive Name](xref:86693dba-d049-4027-874d-d53f0437ad66#configuring-ioboxes).  



![](~/img/BasicPatching_Links_Feedback.png "")   
 

### Feedback Loops
**Creating a loop is not a valid connection!**  
If you really need to do so, you better understand what you're doing.   

For details, see [Creating Feedback Loops](xref:4a3a1653-5c09-4102-a148-8f014f3d9a2e).   



![](~/img/BasicPatching_Links_Segmented.png "")   

### Segmented links
While making a link, just do occasional left clicks. For each click, an anchor point is added. If you later want to edit the shape of a link, select it and drag the little blue squares. To remove anchor points, align them in a straight line.  



![](~/img/BasicPatching_Links_Styles2.png "")   

### Link styles
There are 3 different styles for links:   
* Straight  
* Bezier  
* Vertical-Horizontal-Vertical  
Press CTRL+Y on a selected link to cycle through the styles.   



![](~/img/BasicPatching_RemovingLinksAndKeepingValues.png "")   


### Removing Links
To remove an existing link, first select it (left-click) and then do a right-click on it. (or pressing the BackSpace or Delete key).  

Note that when removing a link, pins with a primitive datatype behave different from Node pins:  

* Primitive data types: **keep their value** when they get disconnected  
* Node pins: **don't keep their value** when they get disconnected. Instead they return to their default  

