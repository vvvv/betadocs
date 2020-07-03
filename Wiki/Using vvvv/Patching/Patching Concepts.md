# Patching Concepts

This is an overview of the most common vvvv patching concepts.  

If you are familiar with textual programming, check the [Programming Concepts](TODO INTERNALLINK:Programming Concepts).  



>note:  
If you're missing a specific concept you can always implement a little plugin using the built-in VL or c# editors.  

* [Dynamic VL Plugin Reference](TODO INTERNALLINK:dynamic-vl-plugin-reference)  
* [Dynamic C# Plugin Reference](TODO INTERNALLINK:dynamic-plugins-reference)  
  



# Loops

![](~/img/PatchingConcepts-Spreading.png "")  

#### Going through a list of items

If you want to go over a list of items and do something to them, you **don't need a loop**.   

vvvv allows you to calculate all desired iterations at the same time using spreads and spectral operations.  

**See:**  
* [Spreads](TODO INTERNALLINK:Spreads)   
* [Spectral Operations](TODO INTERNALLINK:spread-sinks)  



![](~/img/FeedbackLoops_Understanding2.png "")  

#### Accessing previous calculations

If you need to calculate values according to calculations already done in the past (like in an animation where the new position is based on the old one), you need to access these 'old' results from the last frame.  

*It's like accessing local variables.*  

**See:**  
* [Creating Feedback Loops](TODO INTERNALLINK:creating-feedback-loops)  



# If / else

![](~/img/Conditions-SwitchSimple.png "")   



Switching between different inputs or defining whether to do this or that is almost always a part of a patch.  

*It's like working with If, Switch, Case...*  

**See:**   
* [Conditions](TODO INTERNALLINK:conditions)  


# Logical operations

![](~/img/Conditions-Booleans.png "")   



If your patch has to do something IF this OR that is true AND the value is LESS than 42 you need logical operations.  

When patching anything advanced that can be separated into a series of states and events that cause transition from one state to another you are likely looking for <span class="node">Automata (Animation)</span>.  

*It's like all these &&, ||, !=, ...*  

**See:**   
* [Logic](TODO INTERNALLINK:logic)  
* [Conditions](TODO INTERNALLINK:conditions)  



# Constants

![](~/img/patching-constants.png "")   




IOBoxes can be used as constants that are setting values (Colors, Strings...) for Inputs of nodes and subpatches.  

**See:**  
* [IOBoxes](TODO INTERNALLINK:ioboxes)  




![](~/img/patching-parameters.png "")  


Named IOBoxes are used to create Inputs and Outputs for subpatches.  

*It's like input and output parameters of functions.*  

**See:**  
* [Subpatches](TODO INTERNALLINK:subpatches)  


# Send / Receive

![](~/img/patching-send-receive2.png "")  


Values can be sent from one part of a patch to another (or between patches) using the S (=send) and R (=receive) nodes without making any direct links.  

The most common use case for S/R nodes is to deliver global constants to different parts of a project.   

*These are like global variables.*  

**See:**  
* [Send / Receive](TODO INTERNALLINK:send-receive)  


# Spreads

![](~/img/PatchingConcepts-Spreads2.png "")   


Need to make a calculation over many items at the same time or instantly place and animate multiple objects on stage? This is where spreads shine.  

*It's like working with Arrays, Lists, ...*  

**See:**  
* [Spreads](TODO INTERNALLINK:Spreads)  




# SubPatches

![](~/img/BasicPatching_GroupingNodes3_0.png "")   


Instead of duplicating a set of connected nodes you can use subpatches to modularize and structure your patch.  

You can then use many instances of the same subpatch in different parts of your patch. Modifying the subpatch automatically applies the changes to all its instances.   

*It's like functions that take Inputs and return Outputs.*  

**See:**  
* [Subpatches](TODO INTERNALLINK:Subpatches)  



# Storing Values

![](~/img/patching-SpreadCollections.png "")   


If you need to store several values to pick them later, there are several nodes specially for that.  

*It's like working with Buffer, Stack or Queue.*  

**See:**  
* [Spread Collections](TODO INTERNALLINK:spread-collections)  
