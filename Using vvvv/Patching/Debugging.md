---
uid: 36621302-10e7-47fe-a8d0-b609c758974d
---

# Debugging

# Error Console

![](~/img/patchingDebugging_TTY.png "")   

In vvvv errors typically don't break the system. To see if your program experiences any troubles open a [TTY Renderer](xref:e2fe8b35-85de-47a9-a953-2621254e9641) which acts as vvvv's error console.   

In fact it is a good idea to always have a Renderer (TTY) open to be aware of possible problems. Even if you don't understand what a particular error might suggest it may help people on the forum to understand your problem if you post the error there.  


# Finding erroneous nodes


When the TTY Renderer spits out an error similar to this:  
> 
00:00:28 ERR : Exception caused by node during update :/73/245/178/56/101/84 
  
you can find the exact node causing this problem by using the [Finder](xref:869d5933-4693-4b32-a7f3-5b7cfcc3a07f) as follows:  

The sequence "/73/245/178/56/101/84" in the error message above is a path of node IDs from the [root](xref:5eea935d-c82d-4b89-8403-1fbc1d79fb93)) to the actual node causing the problem. In order to find the node you start in the root and type "# 73" into the finder. This will show you the ((subpatches) to open. In this subpatch again you use the finder now to find the second ID from the sequence by typing "# 245" in this example. Continue doing so until you reach the last ID which will point to the erroneous node.   





# Red nodes


A red node has either of 4 problems:   
* it has an input of type Enumeration that is not available on your PC.   
* it is missing   
* it is the wrong CPU architecture  
* it has a runtime error  



![](~/img/Debugging_RedNodes_Enum2.png "")   

#### Missing Enumeration 
In the latter case you'll find the pin colored in red as well and can go there to choose a different value if available. Otherwise you may need to install a driver for the device you're trying to control.   



![](~/img/patchingDebugging_RedNodes_Missing.png "")   



#### Missing Node
If a node is missing, hovering it with the mouse will bring up a tooltip with the path to the file in which vvvv is expecting the node. You can now look for that file on your system and either:  
* dragdrop it onto any open patch which will cause vvvv to add the path of this file to its searchpaths for this session and the red node will magically be replaced. When now saving the patch this directory will be referenced for the formerly red node.  
* add a new searchpath manually in the [Root](xref:5eea935d-c82d-4b89-8403-1fbc1d79fb93) patch  



![](~/img/Debugging_RedNodes_Architecture.png "")   

#### Wrong CPU architecture
Understand that vvvv and all addons come in two flavours: x86 (=32bit) and x64 (=64bit) and you cannot mix them! On modern PCs you'd typically use the x64 build. Only note that some nodes are [missing in 64bit builds](https://vvvv.org/documentation/missing-in-64bit-builds) which would be a reason to still use the x86 builds.   


 

#### Runtime Error
A node may be perfectly running for some time and only experience an occasional runtime error, in which case it turns red to indicate its problem and lead you to it. You have different options to deal with such red nodes:  
* ignore them if they don't do your program any harm. vvvv may still be running fine and only hint to you that this could be a problem under certain circumstances  
* sometimes it may help to re-initialize a node using <kbd>ALT</kbd>+rightclick on the node. But beware that even though this may help temporarily the problem may return at some later point   
* open <span class="node">Renderer (TTY)</span> and see if there is an error message which you could post on the [forum](https://vvvv.org/forums) to ask for help  



![](~/img/patchingDebugging_RedNodes_Runtime.png "")   


A classic example of a node turning red at runtime is the / (Value) when it computes a division by zero.   

A division by zero won't break your program and you can simply ignore it. On the other hand it may give you an interesting hint about another problem in your patch upstream of the node.   

Note that some nodes also have a (hidden) <span class="pin">Error Handling Style</span> which allows you to choose between coloring the node in red or simply ignoring such situations. Also a (hidden) <span class="pin">Success</span> gives you the option to handle an unsuccessful operation in a custom way.   


# Debug Timing


### Framerate
User either of  
* <span class="node">Timing (Debug)</span>  
* <span class="node">PerfMeter (Debug)</span>   
to keep an eye on your framerate.  



![](~/img/Debugging-DebuggingTiming.png "")   

### Timing of the nodes
<kbd>CTRL+F9</kbd>   
toggles debug-mode on/off globally.   
<kbd>SHIFT+CTRL+F9</kbd>   
toggles debug-mode on/off affecting only the currently selected nodes.  

#### Colors
* **red:** slice count changed  
* **green:** pin changed  
* **blue:** pin validated  
* **white:** changed but not validated  

#### Units

Values are expressed in micro seconds. So a value of 130 means 130µs or 0,13ms (milli seconds).   

#### Round Brackets
A value in round brackets on a subpatch means that inside this patch not all nodes are being measured, ie. some have been selectively removed using <kbd>SHIFT+CTRL+F9</kbd>.  
---  
Consult the [Performance](xref:026ac8ca-9bcc-45e4-abf3-ac079a44065b) page if you're looking for gerneral advice to optimize the performance of your patches.   



# Debug Spreads

![](~/img/Debugging-DebuggingSpreads.png "")   


<kbd>CTRL+F10</kbd>  
toggles spreadcounts debug-mode on/off globally.  

A link can have any of 4 styles:  

* **dotted:** when carrying ø  
* **normal:** when carrying 1 slice  
* **thin:** when carrying a slicecount less than half of the patch's maximum spreadcount  
* **thick:** when carrying a slicecount greater then half of the patch's maximum spreadcount  
* **fat:** when carrying the patch's maximum spreadcount  

We hope this to be specifically useful when teaching beginners about spreads or hunting for large spreads or ø.  

