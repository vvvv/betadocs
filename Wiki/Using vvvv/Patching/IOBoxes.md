---
uid: 86693dba-d049-4027-874d-d53f0437ad66
---

# IOBoxes

## Creating IOBoxes

IOBoxes can be used to input (edit) and output (display) data.  

There are 3 ways to create an IOBox:  
* via the [Node Browser](xref:eeb8526d-0085-4219-a138-32ac397853f1) (open it and type IOBox)  
* via a double right-click in a patch  
* via a middle-click while making a connection  


## IOBox flavors

![](~/img/BasicPatching_IOBoxTypes3.png "")   


There is an IOBox for each of the 4 primitive data-types:  
* <span class="node">IOBox (Value Advanced)</span>  
* <span class="node">IOBox (String)</span>  
* <span class="node">IOBox (Color)</span>  
* <span class="node">IOBox (Enumerations)</span>  
All other data-types (like Transform, Texture,...) share one IOBox:  
* <span class="node">IOBox (Node)</span>  


## Configuring IOBoxes

![](~/img/BasicPatching_Inlets_Outlets.png "")   



All IOBoxes have some settings available via config-pins in the [Inspektor](xref:9666611a-6f15-4b33-8300-69f56d9ec7d4) in common:  

#### Name, Pin Visibility
* Descriptive Name  
* Pin Visibility  
are used when creating [SubPatches](xref:b66f153a-f7c3-4867-a8c9-bce69861d759).  

#### Tag
* Tag  
is a string that is not used by vvvv but users can write [plugin](xref:766d8ac2-5145-417d-b2df-37d24e3b2b6f) that access this information.   



![](~/img/BasicPatching-IOBoxSpreading3.png "")   
![](~/img/BasicPatching-SliceOffset3.png "")   


#### Spreading
* SliceCount Mode  
* Columns  
* Rows   
* Pages  
are for spreading IOBoxes.  

Depending on the <span class="pin">SliceCount Mode</span> setting the IOBox has its SliceCount determined by:   
* **Input:** whatever is connected to its input  
* **ColsRowsPages:** the product of *Columns*, *Rows* and *Pages*  
* **Maximum:** whatever of the above is more  

If set to *ColsRowsPages* the product of *Columns* by *Rows* determines how many slices are visible in the IOBox.   

The actual number of slices represented by the IOBox is further determined by the number of visible slices taken by the number of *Pages*.   

If there is more than one page you can use the <span class="pin">SliceOffset</span> to "scroll" through all the available slices.  



![](~/img/BasicPatching_IOBoxConfig2.png "")   

#### Visual properties

* Font   
* Size  
* Show Grid  
* Show SliceIndex   
are used for modifying the display.  


## Displaying Data

![](~/img/BasicPatching_OutputIOBox3.png "")   


In order to display the current value of any output pin in a patch, connect it to an IOBox.   


## Editing Data

![](~/img/patching_InputIOBox.png "")   


In order to specify a constant value for a pin that can easily be tweaked, connect it to an IOBox.   



![](~/img/patching-valueIOBoxValueAndStepSize2.png "")   
![](~/img/BasicPatching_IOBoxValueTypes.png "")   


### Value

* Left-doubleclick to enter a new value (also try math formulas).  
* Alt+Rightclick to reset to default value.  

**Real and Integer Values**  

Right-drag in the IOBox vertically to change its value and optionally modify the stepsize by pressing:  
* SHIFT to divide by 10  
* CTRL to divide by 10  
* CTRL+SHIFT to divide by 100  
* ALT+SHIFT to multiply by 10  
* ALT+CTRL to multiply by 10  
* ALT+CTRL+SHIFT to multiply by 100  

**Boolean values**  

* 'Toggle': right-click to switch between 0 and 1.  
* 'Bang': right-click to set 1 for one frame, else 0.  
* 'Press':  right-press to set 1 as long as mouse is pressed, else 0.  

**Slider**  
* Right-drag to change it.  

Press F1 on an IOBox to get different readily configured options that you can copy-paste into your patches as needed.   




![](~/img/BasicPatching_ColorIOBox3.png "")   

### Color
Right-drag:  

* horizontally to change hue  
* vertically to change brightness   
* vertically and press CTRL to change saturation  
* vertically and press SHIFT to change alpha  

The Color IOBox has several 'Chooser Styles', see [Inspektor](xref:9666611a-6f15-4b33-8300-69f56d9ec7d4):  
* HSVA Field (default)  
* RGBA Slider  
* HSVA Slider  




![](~/img/BasicPatching_StringIOBox.png "")   

### String
Right click in the IOBox to invoke the operation according to its subtype, see [Inspektor](xref:9666611a-6f15-4b33-8300-69f56d9ec7d4):  
* most cases simply open a field to enter text   
* *filename* - open dialog will pop up  
* *directory* - open dialog will pop up  

Note that no matter what subtype the string is if you press CTRL while right clicking the file-open dialog will appear. Pressing SHIFT will invoke the directory-open dialog.  



![](~/img/BasicPatching_IOBoxEnum.png "")   

### Enumeration

Right-click in the IOBox to open up the pull-down menu, choose an item with a left- or right-click.  

The enumeration IOBox can also be switched into a 'List' mode. Open the Inspektor and change the <span class="pin">Style</span> configuration pin.  


## Green IOBoxes

![](~/img/BasicPatching_Kontrolleur.png "")   


IOBoxes tinted green are exposed for being controlled from the outside. Use **CTRL+K** to toggle exposing. See [Kontrolleur](xref:c8fd4535-8b7a-4861-abf1-580520daff26) for more information.   

