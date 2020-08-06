---
uid: 11e284ec-b6b0-47b2-bed3-f90a91e55e91
---

# Patching Concepts

This is an overview of the most common vvvv patching concepts.  

If you are familiar with textual programming, check the [Programming Concepts](xref:87d944e5-aeae-451e-839d-58932488ed6e).  



>note:  
If you're missing a specific concept you can always implement a little plugin using the built-in VL or c# editors.  

* [Quick Reference](xref:2879ae37-9e84-42ee-8e2e-8444d274bb6b)  
* [Dynamic C# Plugin Reference](xref:9fb98fc4-377b-49be-87ee-2c4741183b7c)  
  



## Loops

![](~/img/PatchingConcepts-Spreading.png "")  

#### Going through a list of items

If you want to go over a list of items and do something to them, you **don't need a loop**.   

vvvv allows you to calculate all desired iterations at the same time using spreads and spectral operations.  

**See:**  
* [Spreads](xref:00327d1e-65ba-4424-997d-615d9a469503)   
* [Spectral Operations](xref:81251c9c-350f-462d-9d61-6d81a6896ad9)  

#### Accessing previous calculations

![](~/img/FeedbackLoops_Understanding2.png "") 

If you need to calculate values according to calculations already done in the past (like in an animation where the new position is based on the old one), you need to access these 'old' results from the last frame.  

*It's like accessing local variables.*  

**See:**  
* [Creating Feedback Loops](xref:4a3a1653-5c09-4102-a148-8f014f3d9a2e)  



## If / else

![](~/img/Conditions-SwitchSimple.png "")   



Switching between different inputs or defining whether to do this or that is almost always a part of a patch.  

*It's like working with If, Switch, Case...*  

**See:**   
* [Conditions](xref:69bdb72a-3e21-4b27-a4a6-c15e7c0ec56e)  


## Logical operations

![](~/img/Conditions-Booleans.png "")   



If your patch has to do something IF this OR that is true AND the value is LESS than 42 you need logical operations.  

When patching anything advanced that can be separated into a series of states and events that cause transition from one state to another you are likely looking for <span class="node">Automata (Animation)</span>.  

*It's like all these &&, ||, !=, ...*  

**See:**   
* [Logic](xref:12c13306-f4f1-49f6-84b0-f7808f4214e6)  
* [Conditions](xref:69bdb72a-3e21-4b27-a4a6-c15e7c0ec56e)  



## Constants

![](~/img/patching-constants.png "")   




IOBoxes can be used as constants that are setting values (Colors, Strings...) for Inputs of nodes and subpatches.  

**See:**  
* [IOBoxes](xref:86693dba-d049-4027-874d-d53f0437ad66)  




![](~/img/patching-parameters.png "")  


Named IOBoxes are used to create Inputs and Outputs for subpatches.  

*It's like input and output parameters of functions.*  

**See:**  
* [SubPatches](xref:b66f153a-f7c3-4867-a8c9-bce69861d759)  


## Send / Receive

![](~/img/patching-send-receive2.png "")  


Values can be sent from one part of a patch to another (or between patches) using the S (=send) and R (=receive) nodes without making any direct links.  

The most common use case for S/R nodes is to deliver global constants to different parts of a project.   

*These are like global variables.*  

**See:**  
* [Send / Receive](xref:32b954be-83f1-4b75-951f-f64e7fdd7c1b)  


## Spreads

![](~/img/PatchingConcepts-Spreads2.png "")   


Need to make a calculation over many items at the same time or instantly place and animate multiple objects on stage? This is where spreads shine.  

*It's like working with Arrays, Lists, ...*  

**See:**  
* [Spreads](xref:00327d1e-65ba-4424-997d-615d9a469503)  




## SubPatches

![](~/img/BasicPatching_GroupingNodes3_0.png "")   


Instead of duplicating a set of connected nodes you can use subpatches to modularize and structure your patch.  

You can then use many instances of the same subpatch in different parts of your patch. Modifying the subpatch automatically applies the changes to all its instances.   

*It's like functions that take Inputs and return Outputs.*  

**See:**  
* [Subpatches](xref:b66f153a-f7c3-4867-a8c9-bce69861d759)  



## Storing Values

![](~/img/patching-SpreadCollections.png "")   


If you need to store several values to pick them later, there are several nodes specially for that.  

*It's like working with Buffer, Stack or Queue.*  

**See:**  
* [Spread Collections](xref:bdc0b656-7f64-4cb5-a7bc-eac1c28a8357)  
