# Programming Concepts

You are familiar with textual programming and are missing some of the basic concepts of your mother tongue in vvvv?  

Here is collection of common programming concepts and some hints to where you can find them in vvvv.  

If you're not a coder, check [Patching Concepts](TODO INTERNALLINK:Patching Concepts).  


>note:  
If you're missing a specific concept you can always implement a little plugin using the built-in VL or c# editors.  

* [Dynamic VL Plugin Reference](TODO INTERNALLINK:dynamic-vl-plugin-reference)  
* [Dynamic C# Plugin Reference](TODO INTERNALLINK:dynamic-plugins-reference)  
  


# Classes, Custom Datatypes, Functions

![](~/img/patching-subpatches.png "")   



There is no concept of classes in vvvv. For basic structuring of your programs have a look at [Subpatches](TODO INTERNALLINK:Subpatches).  

Subpatches can be understood as functions that take Inputs and return Outputs.  

There've been attempts to add further ways of structuring data into vvvv, see:  
* <a href="https://vvvv.org/contribution/message-2.0" class="extURL contribution" target="_blank">Message</a> by <span class="user"><a href="https://vvvv.org/users/velcrome" class="extURL" target="_blank">velcrome</a></span>  
* <a href="https://vvvv.org/contribution/vobjects" class="extURL contribution" target="_blank">VObjects</a> by <span class="user"><a href="https://vvvv.org/users/microdee" class="extURL" target="_blank">microdee</a></span>  
* <a href="https://github.com/woeishi/VVVV.Struct" class="extURL" target="_blank">VVVV.Struct</a> by <span class="user"><a href="https://vvvv.org/users/woei" class="extURL" target="_blank">woei</a></span> & <span class="user"><a href="https://vvvv.org/users/tonfilm" class="extURL" target="_blank">tonfilm</a></span>  


# Conditions

![](~/img/Conditions-SwitchSimple.png "")   



Looking for an *if*, *switch*, ...?  

See [Conditions](TODO INTERNALLINK:conditions).  


# Loops


![](~/img/patching-spectral2.png "")  


Where in textual programming you’d use a **for, while** or **repeat** construct to execute some lines of code multiple times before going on executing the rest of the program, this is not possible with vvvv.   

Basically vvvv avoids the concept of such sequential loops. Instead it often allows you to calculate all desired iterations at the same time using **spectral operations**.  

See [Spread Sinks](TODO INTERNALLINK:spread-sinks).  


# Variables

![](~/img/patching-send-receive2.png "")  


#### Global Variables
Values can be sent from one part of a patch to another (or between patches) using the S (=send) and R (=receive) nodes without making any direct links.  

The most common use case for S/R nodes is to deliver global constants to different parts of a project.   

See [Send / Receive](TODO INTERNALLINK:send-receive).  




![](~/img/patching-var-loop4.png "")   


#### Local Variables
In order to save the result of a computation in one frame to use it for further calculation in the next you have to use a node called *FrameDelay*. Essentially by setting its input you write a local variable which you can read from in the next frame by connecting to its output.  

FrameDelay nodes are therefore creating feedback-loops in a patch.  

See [Creating Feedback Loops](TODO INTERNALLINK:creating-feedback-loops).  




![](~/img/patching-constants.png "")   


#### Constants
IOBoxes can be used as constants, which are feeding manually adjusted Values (Colors, Strings...) for Inputs of the nodes and subpatches.  

See [IOBoxes](TODO INTERNALLINK:ioboxes).  





![](~/img/patching-parameters.png "")  


#### Input/Output Parameters
Named IOBoxes are used to create Inputs and Outputs for subpatches. They can therefore be understood as **input** and **output parameters** of **functions**.  

See [Subpatches](TODO INTERNALLINK:subpatches).  



# Collections

![](~/img/Spreads_ColsAndRows_Output2.png "")   


Looking for an *Array*, *List*, ...?  

See [Spreads](TODO INTERNALLINK:Spreads).  


# Data Storages

![](~/img/patching-SpreadCollections.png "")   




Looking for a *Buffer*, *Stack* or *Queue*?  

See [Spread Collections](TODO INTERNALLINK:spread-collections).  


# Null

![](~/img/patching-nil.png "")  


An empty Array or List in textual language is Nil in vvvv.  

See [NIL](TODO INTERNALLINK:spread-definitions#nil).  


# State Automatas

![](~/img/patching-automata.png "")  


When patching anything that can be separated into a series of states and events that cause transition from one state to another you are likely looking for <span class="node">Automata (Animation)</span>. Also the [Timerliner](TODO INTERNALLINK:timelinersa#automata) has an automata built in.  

**See also:**  
* [Graphic Automata](TODO INTERNALLINK:graphicalautomata)  


