---
uid: 9666611a-6f15-4b33-8300-69f56d9ec7d4
---

# Herr Inspektor


![](~/img/vvvv_HerrInspektor.png "")  



Herr Inspektor is giving you an overview of the settings of all the pins of a selected node. If you want to view or edit multiple and/or normally invisible parameters, it is often necessary to open an Inspektor.  

#### How to open
* <span class="keyseq"><kbd>Ctrl</kbd><kbd>I</kbd></span>   
* <span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>I</kbd></span> for additional Inspektor Windows  

When an Inspektor is already open pressing <span class="keyseq"><kbd>Ctrl</kbd><kbd>I</kbd></span> will just bring that (or any) Inspektor to the front and not create a new instance. To create multiple instances use <span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>I</kbd></span>.  

#### Structure
The Inspektor's view is structured into 3 sections:  
* Configuration Pins: only visible in the Inspektor  
* Input Pins: editable input pins  
* Output Pins: readonly output pins  

#### Editing values
Values in the Inspektor are changed the same way as in IOBoxes. Basically that means: **rightclick** (strings, enums) or **rightclick+drag** (values, colors). For details see [Editing IOBoxes](xref:86693dba-d049-4027-874d-d53f0437ad66#editing-data).  

#### Pin Visibility
The narrow column of quads on the very left indicates the visibility of a pin in the patch. By clicking the quads you can toggle the respective pins between *Visible*, *Hidden* and *OnlyInspektor*.  

#### Attaching Inspektor
Usually all Inspektors always adapt to the currently selected node. If you want to permanently edit a specific node with a specific Inspektor, you can attach an Inspektor to the current selection by pressing the **'Attach to Selection'** button. You can create additional Inspektors for editing other nodes by pressing <span class="keyseq"><kbd>Ctrl</kbd><kbd>Shift</kbd><kbd>I</kbd></span>.  

#### Multiple nodes at once
When selecting multiple nodes at once the Inspektor only shows pins that all those nodes have in common.   

**See also:**  
* [Inspektor Tutorial](xref:61440fc4-4815-406c-b97a-c0abfd97cd6f)  
* [Video Tutorial](xref:09f00508-01d4-4eac-b6d3-4dace5b00d99#tutorial-8-herr-inspektor)  



