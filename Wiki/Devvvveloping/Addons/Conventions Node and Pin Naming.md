---
uid: db8592a2-03c3-4e8c-a540-d11df5e83078
---

# Conventions Node and Pin Naming
When writing a new node and you are not sure about naming come here and find a solution.   

# Nodes/Modules
All terms (names, categories, versions) (except pin names, see below) are written in <a href="http://en.wikipedia.org/wiki/CamelCase" class="extURL" target="_blank">CamelCaps</a>  

**NodeName (Category OptionalVersion1 OptionalVersion2 .. )**  
	
### Rules for choosing a name
* nodenames must be a single word without spaces  

* if you are mainly encapsulating a function of a library it may make sense to stick to that name. for all the dx-nodes we tried to stay close to the dx-sdk for example, so that people who know dx (or your library) easily find their way in vvvv.  

* make it a general associative term. if your node does something strange like the "Stallone" node feel free to choose your own association.   

* as with the Trautner, Delauny and Gouraud nodes... name a node by the inventor of the technique implemented  

### Rules for choosing a Category
* a category is mandatory  
* it starts with a capital letter  
* it must only be a single word  
* prefer to use one of the existing categories over inventing a new one.  

### Rules for choosing optional Versions
* for most nodes leaving this blank is the best option  
* do not use this version to indicate a specific version (as in "revision") of that particular node.  
* only use this to distinguish two nodes that do basically the same but only can be set apart by a subtle detail (see the many IO nodes in the "devices" category for examples)  
* in the rare case where you need to specify multiple versions, separate them by space.  


### Rules for choosing optional Tags
read [About Tags](xref:9ba99c9e-2f8c-4987-a028-95bd35b88ec9)  

# Pins 
* pin names start with capital letter   
* instead of using CamelCaps separate the words here, like: "Transform Mesh" instead of "TransformMesh"  
* keep names generic. If they have no special meaning name them: Input, Output (this helps vvvv to automatically reconnect pins when exchanging similar nodes)  
* make use of the [AutoName (VVVV DescriptiveName)](https://vvvv.org/tiki-download_file.php?fileId=1783")-module to stick really to the conventions.  

### Configuration Pins:
Configuration pins are primarily pins that must not be changed programmatically in a running patch (e.g. since they would add/remove pins on their nodes)  

### Input Pins with Subtype *Bang*
Try to use one of the following:  
* Apply (instead of: DoIt, ...)  
* Update (instead of: Refresh, Reassign..)  
* Read  
* Write  
* Copy  
* Move  
* Reset   
Don't use names like "Do Read", an imperative "Read" is enough. 