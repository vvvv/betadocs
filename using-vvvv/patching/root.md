---
uid: 5eea935d-c82d-4b89-8403-1fbc1d79fb93
---

## The Concept

![](~/img/BasicPatching_Cascading.png "")  
 
*Cascading structure of subpatches as seen in the [Finder](xref:869d5933-4693-4b32-a7f3-5b7cfcc3a07f) window*  


The Root patch is the patch on top of the [SubPatches](xref:b66f153a-f7c3-4867-a8c9-bce69861d759). It is the only patch that does not have a parentpatch.   

The root patch automatically loaded on start up is the "root.v4p" file next to vvvv.exe. Typically it does not have to be changed. But if you like, you can use it just like any other patch and add nodes and subpatches to it.   

Press <span class="keyseq"><kbd>ALT</kbd><kbd>R</kbd></span> to open it.   

So you may change that patch to fit your needs, but be sure to save it manually whenever you are happy, since you won't be asked to save the file when closing vvvv.  

The Root patch typically contains   
* nodes that configure vvvv, like <span class="node">MainLoop (VVVV)</span>, <span class="node">NodeList (VVVV)</span>  
* GUI nodes like <span class="node">Finder (VVVV)</span>, <span class="node">Inspektor (VVVV)</span> or <span class="node">ProjectExplorer (VVVV)</span>  
* node of temporary patches and patches that you opened via the windows explorer  

---  

If you close the root patch vvvv will ask what if you want to:  
* open an existing patch  
* create a new patch  
* quit  


## Custom Root



Instead of opening the default "root.v4p" file that ships with vvvv you can also open any other patch as root using one of these two methods:  
* in windows explorer right-click a .v4p file and choose "Open as Root".   
* use the /r [commandline](xref:2eb3d2a2-d4c1-4bc0-bcd8-16e48d756b16) option  
