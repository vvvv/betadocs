---
uid: 869d5933-4693-4b32-a7f3-5b7cfcc3a07f
---

# Finder


![](~/img/vvvv_Finder2.png "")   



The Finder gives you an overview of the currently loaded patch hierarchy and quickly lets you find nodes in your patches.   

**How to open:**  
* **Ctrl+F**   
* **Ctrl+Shift+F** for additional Finder Windows  

It's not necessary to click on the text field, its active as soon as the finder window is active.   

Move the mouse over the text field to see the tag list that allows for some quick filtering. Note that all those tags come into effect only when followed by a space.  


#### Search Scope
By default only nodes in the active patch are searched.   
Via the following tags you can expand the scope:  
**<** - search globally in the whole graph  
**>** - search in patches within the active patch  

Check [the complete list of tags](TODO INTERNALLINK:finder#filter-nodes) to filter particular nodes.  

If you also want to search inside [modules](TODO INTERNALLINK:subpatches#modules) activate the **M** checkbox in the topright corner of the finder.  


#### Mouse Interaction
* **Leftclick** a node to focus and select it in the patch (if the patch is visible)  
* **Doubleclick** a node: same as above but opens patch if hidden  
* **Rightclick** a node to show its GUI/Editor (in local scope RightClicking the active patch goes one level up)  
* **RightDrag** to scroll canvas  
* **MouseWheeel** to zoom canvas  
* **Rightclick** the tag-textfield to clear it  


