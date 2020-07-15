---
uid: b66f153a-f7c3-4867-a8c9-bce69861d759
---

# Subpatches

## The Concept



Visual programming tends to create huge and complex structures, which may look beautiful at times, but if you're seriously working on a little bigger project you'll soon want to use subpatches to modularize your work.   




![](~/img/SubPatches-Concept2.png "")  
*A patch and its subpatch (as a node and [InABox](TODO INTERNALLINK:the-gui#window-modes) )*  


The term *Subpatch* refers to a patch that is used as a node inside another patch. Thus the term describes only a specific point of view. In fact every subpatch is an ordinary patch that is only called a subpatch when referred to from the patch its node is placed in. Likewise we can call a patch a *Parentpatch* when we're referring to the patch that holds the node of the patch we're talking about.   

An example:  
>Patch**1** contains Patch**2**.  
seen from Patch**1**: Patch**2** is a Subpatch  
seen from Patch**2**: Patch**1** is its ParentPatch  

In other words: a patch can contain many subpatches but each patch only has one parentpatch.   



![](~/img/BasicPatching_Cascading.png "")  
 
*Cascading structure of subpatches as seen in the [Finder](TODO INTERNALLINK:the-gui#finder) window*  


According to this definition every patch that we see is also represented as a node in some other patch forming a hierarchy of patches. The top of this hierarchy is called the [Root](TODO INTERNALLINK:Root) and can always be opened via the shortcut **ALT+R**.  



 


It may also help to understand that subpatches are only a visual clue to the user but vvvv does not understand them. In fact to vvvv it does not matter if you put all your nodes in one huge patch or use subpatches to cleverly structure your program and make it human readable.   

---  

Learning when and where to best modularize, ie. where to draw the line between one patch and its subpatch(es) is one of the biggest challenges when learning the art of patching/programming. If you're up for some general tips read: [Software Engineering Patterns with vvvv](TODO INTERNALLINK:software-engineering-patterns-with-vvvv).  



![](~/img/patchingSubpatches_Finder.png "")   

### Finder
In order to get an overview of all the nodes in a patch or even the whole hierarchy of your programs patches open the [Finder](TODO INTERNALLINK:the-gui#finder) or use CTRL+TAB to cycle through all open windows.  



## Creating a Subpatch

![](~/img/BasicPatching_GroupingNodes3_0.png "")   


There are two ways to create a subpatch:  
* automagically (by grouping nodes)  
* manually (by labeling IOBoxes)  

### Grouping Nodes
Select a group of nodes that you want to collapse into one node and press **CTRL+G**. This will cut those nodes, paste them in a subpatch and keep all connections to nodes that were not in the selection.  

Note that the name of the node/subpatch at this point is quite generic. It is therefore advised that you now rightclick the new node and then press **CTRL+SHIFT+S** in order to *Save As...* it under a suitable name.   

Also you may want to have a look at the <span class="pin">Descriptive Name</span> of the IOBoxes that were automatically inserted and give them more meaningful names where applicable.   



![](~/img/patching-parameters_0.png "")   





### Labeling IOBoxes
Create a new empty subpatch within the current patch by pressing **CTRL+SHIFT+P**. Place nodes in that patch as desired and create IOBoxes for all values that you want to take into or return from that patch. Set a <span class="pin">Descriptive Name</span> via the Inspektor or by a simple middle-click on the IOBox in order to make them show up as inlets/outlets on the patches node.   

Press **CTRL+SHIFT+S** in order to *Save As...* the patch under a suitable name.   



![](~/img/Subpatches-Visibility.png "")   



### Pin Visibilty
A pins visiblity can always be changed by the user [via the Inspektor](TODO INTERNALLINK:the-gui#pin-visibility). As the designer of a subpatch you can define a default for the pin represented by each IOBox by setting the <span class="pin">Pin Visibility</span> of the IOBox to the respective value.  



![](~/img/Subpatches-ChangedInputs3.png "")   

### Detecting changed Inputs
Each IOBox has a hidden <span class="pin">Changed</span> output that can be used to detect if its input has changed. You can activate this output by changing its [visibility](TODO INTERNALLINK:the-gui#pin-visibility) via the Inspektor.  

Use it to only make a subpatch calculate its outputs when any of its inputs has changed. Alternatively create an <span class="pin">Enabled</span> input to let the user of the subpatch control its execution.   



![](~/img/Subpatches-BinSize2.png "")   



### Dealing with BinSize
If you want your subpatch to expose a <span class="pin">Bin Size</span> for an input then make sure to use one of the handy NormalizeBinSize nodes (available for many categories). It simplifies working with [Bins and Bin Sizes](TODO INTERNALLINK:spread-definitions#bins-and-bin-sizes) within a subpatch in that it translates a given bin size (positive or negative) into the actual bins you'll have to calculate with.   


## Instantiating a Subpatch

![](~/img/SubPatches-Instancing.png "")   




You can create an instance of a subpatch like any other node using the NodeBrowser. Type **'t '** (t followed by Space) to filter only for subpatches in the current patchs directory.   

Multiple instances of a subpatch can happily co-exist and still compute their own data.   

**But beware** that if you change anything inside a subpatch that obviously changes for all instances!  

### Encapsulation
A subpatch can include an instance of another subpatch which in turn can include an instance of another subpatch and so on. There is no limit to this encapsulation.   

### Recursion
A subpatch can not include an instance of itself! vvvv will not allow you to patch such a recursion. Many recursive algorithms can be solved in an alternative way. See [Spread Sinks](TODO INTERNALLINK:spread-sinks) for a hint or look into programming your own [plugin](TODO INTERNALLINK:plugins) in c# to solve such a particular problem.  



## Closing vs. Hiding Windows of Patches




When handling the windows of patches make sure you understand the difference between closing and hiding. Please refer to [Window Modes](TODO INTERNALLINK:the-gui#window-modes) for details.  

Also note that you can stack windows on top of each other to save precious screenspace. Please refer to [Docking](TODO INTERNALLINK:the-gui#docking) for details.   


## Controlling Evaluation

![](~/img/SubPatches-Evaluation2.png "")   
*3 scenes with the [Timing Debug-Mode](TODO INTERNALLINK:debugging#debug-timing) turned on.*  



It is sometimes desireable to pause evaluation of a subpatch when its output is not needed. Note that every subpatch-node has an <span class="pin">Evaluate</span> only visible in the [Inspektor](TODO INTERNALLINK:the-gui#herr-inspektor) by default.  

Disabling this pin stops the evaluation of this subpatch (and of course also all of its children).   

>note:  
Never put nodes that receive inputs from a physical device (like the mouse-nodes, UDP, TCP, Midi, ...) in a patch that you disable. Those nodes may still be collecting input even when in a patch that is disabled which may result in an unexpected behavior the moment you re-enable evaluation for that patch.  
  



## Modules

![](~/img/SubPatches-Modules.png "")   




Modules are basically ordinary patches that are mostly created to be used as black-boxes (ie. without the user typically looking inside them). In order to make patch into a module follow these steps:  
* press **Ctrl-M** and add Author, Description and Tags  
* give your patch a name with a category in the round brackets, like **Slope (2d).v4p**.   
* see all [Naming Conventions](TODO INTERNALLINK:Conventions.NodeAndPinNaming)  
* optional: add a helppatch, see [Helppatch Conventions](TODO INTERNALLINK:Conventions.HelpPatch)  
