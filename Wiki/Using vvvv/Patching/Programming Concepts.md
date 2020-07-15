---
uid: 87d944e5-aeae-451e-839d-58932488ed6e
---

# Programming Concepts

You are familiar with textual programming and are missing some of the basic concepts of your mother tongue in vvvv?  

Here is collection of common programming concepts and some hints to where you can find them in vvvv.  

If you're not a coder, check [Patching Concepts](xref:11e284ec-b6b0-47b2-bed3-f90a91e55e91).  


>note:  
If you're missing a specific concept you can always implement a little plugin using the built-in VL or c# editors.  

* [Quick Reference](xref:2879ae37-9e84-42ee-8e2e-8444d274bb6b)  
* [Dynamic C# Plugin Reference](xref:9fb98fc4-377b-49be-87ee-2c4741183b7c)  
  


# Classes, Custom Datatypes, Functions

![](~/img/patching-subpatches.png "")   



There is no concept of classes in vvvv. For basic structuring of your programs have a look at [Subpatches](xref:b66f153a-f7c3-4867-a8c9-bce69861d759).  

Subpatches can be understood as functions that take Inputs and return Outputs.  

There've been attempts to add further ways of structuring data into vvvv, see:  
* <a href="https://vvvv.org/contribution/message-2.0" class="extURL contribution" target="_blank">Message</a> by <span class="user"><a href="https://vvvv.org/users/velcrome" class="extURL" target="_blank">velcrome</a></span>  
* <a href="https://vvvv.org/contribution/vobjects" class="extURL contribution" target="_blank">VObjects</a> by <span class="user"><a href="https://vvvv.org/users/microdee" class="extURL" target="_blank">microdee</a></span>  
* <a href="https://github.com/woeishi/VVVV.Struct" class="extURL" target="_blank">VVVV.Struct</a> by <span class="user"><a href="https://vvvv.org/users/woei" class="extURL" target="_blank">woei</a></span> & <span class="user"><a href="https://vvvv.org/users/tonfilm" class="extURL" target="_blank">tonfilm</a></span>  


# Conditions

![](~/img/Conditions-SwitchSimple.png "")   



Looking for an *if*, *switch*, ...?  

See [Conditions](xref:69bdb72a-3e21-4b27-a4a6-c15e7c0ec56e).  


# Loops


![](~/img/patching-spectral2.png "")  


Where in textual programming you’d use a **for, while** or **repeat** construct to execute some lines of code multiple times before going on executing the rest of the program, this is not possible with vvvv.   

Basically vvvv avoids the concept of such sequential loops. Instead it often allows you to calculate all desired iterations at the same time using **spectral operations**.  

See [Spectral Operations](xref:81251c9c-350f-462d-9d61-6d81a6896ad9).  


# Variables

![](~/img/patching-send-receive2.png "")  


#### Global Variables
Values can be sent from one part of a patch to another (or between patches) using the S (=send) and R (=receive) nodes without making any direct links.  

The most common use case for S/R nodes is to deliver global constants to different parts of a project.   

See [Send / Receive](xref:32b954be-83f1-4b75-951f-f64e7fdd7c1b).  




![](~/img/patching-var-loop4.png "")   


#### Local Variables
In order to save the result of a computation in one frame to use it for further calculation in the next you have to use a node called *FrameDelay*. Essentially by setting its input you write a local variable which you can read from in the next frame by connecting to its output.  

FrameDelay nodes are therefore creating feedback-loops in a patch.  

See [Creating Feedback Loops](xref:4a3a1653-5c09-4102-a148-8f014f3d9a2e).  




![](~/img/patching-constants.png "")   


#### Constants
IOBoxes can be used as constants, which are feeding manually adjusted Values (Colors, Strings...) for Inputs of the nodes and subpatches.  

See [IOBoxes](xref:86693dba-d049-4027-874d-d53f0437ad66).  





![](~/img/patching-parameters.png "")  


#### Input/Output Parameters
Named IOBoxes are used to create Inputs and Outputs for subpatches. They can therefore be understood as **input** and **output parameters** of **functions**.  

See [SubPatches](xref:b66f153a-f7c3-4867-a8c9-bce69861d759).  



# Collections

![](~/img/Spreads_ColsAndRows_Output2.png "")   


Looking for an *Array*, *List*, ...?  

See [Spreads](xref:00327d1e-65ba-4424-997d-615d9a469503).  


# Data Storages

![](~/img/patching-SpreadCollections.png "")   




Looking for a *Buffer*, *Stack* or *Queue*?  

See [Spread Collections](xref:bdc0b656-7f64-4cb5-a7bc-eac1c28a8357).  


# Null

![](~/img/patching-nil.png "")  


An empty Array or List in textual language is Nil in vvvv.  

See [NIL](xref:a2b935e8-17cd-4c26-b701-4919803792d1#nil).  


# State Automatas

![](~/img/patching-automata.png "")  


When patching anything that can be separated into a series of states and events that cause transition from one state to another you are likely looking for <span class="node">Automata (Animation)</span>. Also the [Automata](xref:76f3717c-5da9-4a2a-9d53-4c5b982291a6#automata) has an automata built in.  

**See also:**  
* [Graphic Automata](xref:250959b9-c2b3-420e-ad36-0b7c6b784fb6)  


