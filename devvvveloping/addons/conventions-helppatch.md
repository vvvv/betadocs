---
uid: 07824e2d-da59-4df0-9f49-a143dc0f7625
---

# Conventions HelpPatch
A HelpPatch demonstrates the functionality of a node. Ideally a novice should quickly get an idea of what the node is about and an expert should get detailed information on its usage.   

## Design Tips

* create a helppatch for a node by selecting it and pressing F1. if the node does not have a helppatch yet, a dummy patch with already the right name will open. simply press <span class="keyseq"><kbd>CTRL</kbd><kbd>S</kbd></span> to save the patch to disk and then start modifying it.  

* first find the most simple usage scenario of a node which will give the novice a quick overview  
* now explain the node a second time with a more advanced usage scenario and put that graph right next to the simple scenario  
* find further scenarios if applicable and place them right next to the existing  

* create IOBoxes for input pins that you set to values other than their default  
* don't label them (as if they were inputs) but write a comment next to them and explain their usage  

* in all your texts/comments please stick to the [Conventions.NodeAndPinNaming](xref:db8592a2-03c3-4e8c-a540-d11df5e83078).  
* create a *see also* section where you place related nodes that the user is supposed to also checkout.   
* add links to online information (wikipedia,..) regarding the functionality of the node  

## Contribute
If you want your helppatch included with the next release please add them to this forum thread: <a href="https://discourse.vvvv.org/t/missing-helppatches" class="extURL forum" target="_blank">missing-helppatches</a>