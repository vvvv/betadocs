---
uid: c2669d6a-c5b6-4260-aa6a-bc8dea458297
---

# Creating an Effect
There are different ways to create effect nodes in vvvv. You can simply instantiate any of the effects that ship with vvvv by selecting them in the nodelist from the EX9.Effect category.   

You can also dragdrop any effect file (with the extension .fx) onto a patch or from the menu select *Open in Patch* and select an effect file.  

If you want to create an all new effect it is best to start from a simple template, that has the basic structure already laid out. The <span class="node">Template (EX9.Effect)</span> node is what you're looking for. In the NodeBrowser look for this node but instead of simply creating it, clone it via <span class="keyseq"><kbd>CTRL</kbd><kbd>Enter</kbd></span> or <span class="keyseq"><kbd>CTRL</kbd><kbd>Click</kbd></span>. Give it a new unique name and vvvv will make a copy of the template you can now start from.  

# Pins
Looking at effect nodes you'll see a few pins all of them have in common:  

**Inputs**  
* Render State: here you can connect any of the nodes from the EX9.RenderState category  
* Mesh: connect a mesh (geometry) to be rendered with the given effect.   
* Transform: here you connect the world transformation for the mesh   
* Technique: an enumeration of all the techniques in the effect  
* Technique Pass: here you specify the passes to be rendered. ut in a spread of values, the effect node will then render the given passes in the order of the spread. To render all passes of a technique, set the passes pin to -1 (default value).  
* Enabled: switch the rendering on and off. works slicewise!  

**Outputs**  
* Layer: connect this to a renderer  
* Compiled: boolean telling you if the effect is compiled  
* Technique Valid: spread of booleans telling you if the individual techniques are valid on your gpu  
* Description: a summary of the effects innards.  

The Pins representing the parameters in the effect are added according to the effect code. Note that vvvv can not interpret the structure of the effect as long as there are errors in the code and compilation fails.   

# Spreading Effects
**todo: mesh subsets, arrays**  

# Editing the effect code
To edit the code, rightclick the effect node and an editor window will pop up.   

In the main text view you can directly edit the code. Simply start typing to be assisted with a codecompletion window that also includes a listing of all <a href="http://msdn.microsoft.com/en-us/library/ff471376(v=VS.85).aspx" class="extURL" target="_blank">HLSL intrinsic functions</a>. Press Ctrl+S to save and compile the effect.  

If there are errors compiling the effect, they will be displayed in the lower part of the editor window. You can doubleclick any of the errors to jump to the line that contains the error.   

Note: if you have several effect nodes of one Effect File open at a time, changing the code of one instance will automatically change the code of all effect nodes of that effect file, which is just the same behaviour as with patches. 