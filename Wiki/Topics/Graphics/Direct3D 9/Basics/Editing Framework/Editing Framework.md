---
uid: f08a1468-aab9-4228-bb07-e69b316bcd18
---

# Editing Framework
The vvvv editing framework consists of a series of nodes that are useful for editing geometry (points, lines, grids..) directly in a renderer. They've been designed with the following aspects in mind:  


**Persistence**  
Editing state can be saved to and loaded from files  

**Boygrouping**  
Editors can be used in boygrouping scenarios by simply putting a halfboygrouped module (provided) between Editor and View  

**Undo/Redo**  
Editing steps can be undone/redone  

**Modularity**  
A clear line between Model and View allows for:  
* easy reuse of individual parts in custom editors   
* a simple way to adapt the look of an editor by simply providing an alternative View module  
* DX9 and DX11 versions of the View modules  


