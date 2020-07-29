---
uid: 2b6364c7-c8a5-4e02-86df-da55f233b5cb
---

# Finder in Detail

**Ctrl+F** opens the Finder window. If you want to open additional Finder windows press **Ctrl+Shift+F**.   

Search is tag-based. Type more tags (separated by space) to refine your search.   

Additionally the following 1-character tags allow you to do some quick filtering. Note that all those tags come into effect only when followed by a space.  

>note:  
It's not necessary to click on the text field, its active as soon as the finder window is active. Only hover over the text field if you want to see the tag list.  
  


# Search Scope

By default only nodes in the active patch are searched. Via the following tags you can expand the scope:  
**<** - search globally in the whole graph  
**>** - search in patches downstream of the active patch  



# Filter nodes

Use the following tags to show only:  
**n** - Native nodes  
**m** - Modules  
**p** - vvvv Plugins  
**x** - Effects (shaders)  
**f** - Freeframes Plugins  
**v** - VST Plugins  
**a** - all Addons (modules, plugins, effects, freeframes, VSTs)  
**i** - IOBoxes (of patches/modules)  

**s** - Send/Receive Nodes  
**/** - Comments  
**l** - Labels (descriptive names)  
**t** - Patches  
**r** - Red (missing) Nodes  
**b** - Boygrouped Nodes  
**#** - Node IDs  
**w** - Windows  


# Mouse Interaction

* **Leftclick** a node to focus and select it in the patch (if the patch is visible)  
* **Doubleclick** a node: same as above but opens patch if hidden  
* **Rightclick** a node to show its GUI/Editor (in local scope RightClicking the active patch goes one level up)  
* **RightDrag** to scroll canvas  
* **MouseWheeel** to zoom canvas  
* **Rightclick** the tag-textfield to clear it  

