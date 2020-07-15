---
uid: 32b954be-83f1-4b75-951f-f64e7fdd7c1b
---

# Send-Receive
<span class="include">TODO INCLUDE patchingtoc</span>  

---  

![](~/img/patching-send-receive2.png "")   


Data can be sent from one part of a patch to another (or between patches) using the S (=send) and R (=receive) nodes without making a direct link between pins.  

The most common use case for S/R nodes is to deliver global constants/variables from a central patch to different parts of a project.  

Creating an S node can be compared to assigning a variable. A corresponding R node lists all available variables on its <span class="pin">Receive String</span> and by selecting one of those, it returns the corresponding value.   

Technically there is no difference between creating a link between two pins or using an S/R combo to pass data.  

## Creating via Shortcut
The quickest way to create an S or R node is starting a link from a pin and then pressing CTRL+Middleclick. An S node created this way also automatically has its <span class="pin">Send String</span> set to the connected outputs name.  

## Advanced
The addonpack comes with an alternative version of the nodes labeled "Advanced" provided by <span class="user"><a href="https://vvvv.org/users/vux" class="extURL" target="_blank">vux</a></span>. The differences are:  
* <span class="pin">Receive String</span> is of type string (instead: Enumeration)  
* the same send string can be used on multiple S nodes in which case matching R nodes work in LTP (last takes precedence)  
* attention: for technical reasons the nodes may (or may not) introduce a one frame delay  



# Lost your S/R nodes?

![](~/img/Debugging-SendReceive2.png "")   


If you've got lost where all the S and R nodes are buried in your project, the [Finder](xref:869d5933-4693-4b32-a7f3-5b7cfcc3a07f) is your friend.  

Open the Finder (CTRL+F) and type '**s <**'. It will show you a relation of all the subpatches that contain S and R nodes. Hovering the mouse over any of them shows their connection(s).  

