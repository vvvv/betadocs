---
uid: 754035b5-77f5-4818-9de3-bfa7c1b185a9
---

# Quartz Composer for VVVV users
a few quick notes on quartz composer to get you going on OSX if you're used to vvvv. consider this the notes from a node08 workshop that didn't happen!  

getting it -  
--- quartz composer comes with Mac OSX, but its a developer tool so you'll need to install the developer 'xcode' package. you'll find this on the dvd that came with your mac, or the you can download it from http://developer.apple.com (beware, its like 1gb).  
--- developer things live in /Developer, so its in /Developer/Applications/. better still, just use spotlight to lauch it: apple-space, "qua", return, and it should be loading in front of you.  
--- don't even bother if you're still running tiger. qc in leopard is a mature offering, tiger is painful.  
--- once you've got it, go to the help menu where you'll find links to folders full of example patches  

using it -   
--- the nodes process from left to right, and i try to patch that was too for clarity. you'll find your patches suit widescreen monitors this way too.  
--- the nodes are bigger than vvvv's, but the inputs are named and you can *zoom out* and still patch.  
--- qc evaluates the patch by pulling information from render nodes, which are the red ones. this means that your nodes won't work, sums will show wrong answers etc, unless they're actually being used to generate output.  
--- the 'mathematical expression' node is ultra useful: you can write sums out and it will create the required inputs by parsing it as you type. the real bonus is the readability it brings to your patch: the title of the node displays the equation, and the inputs are correctly named. it also does boolean logic and the ternary operator (ie if?then:else). eg "!not" will turn a 0 to a 1, in a form a lot more compact and readable than the logic node.  
--- if you need something more sophisticated than an equation or a numeric if then else, there is a javascript node that can do similar wonders with named inputs and outputs. you can also keep persistent variables in your javascript using the object class.  
--- there is no transform data type, instead transforms are macro patches that transform whatever is inside them.  
--- there is an essential hidden patch called 'log', which is a renderer by class (thus making everything patched to it start evaluating) but will write number / string input to the console instead. you can enable and disable the hidden patches by toggling the preference via the following terminal command  

extending it -  
--- go to kineme.net for a wealth of third party nodes, and to file feature requests for things you need.  
--- write your own data or image processing nodes using the plug-in api. see the developer documentation.  

a final note -   
qc is not a patch on vvvv, excuse the pun. but what is amazing about it, is that it is not a stand-alone environment, but an image processing framework built into the heart of osx that happens to have an editor application with preview window. so your qc patches should be able to play in any osx application just as a quicktime movie would - they're peers. so go download the vj app vdmx from www.vidvox.net and see what fun you can have, or write your own application featuring qc as its rendering engine.