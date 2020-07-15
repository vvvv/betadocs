---
uid: b54e17f0-5939-4e9e-bdd3-0ef7d2623929
---

# HowTo DMX Advanced
---  
---  
see also **[node08.workshop.DMX](xref:086375e6-a403-472b-84dd-7b95a13bdde2)**  
---  
---  
>**this page created by <span class="user"><a href="https://vvvv.org/users/kalle" class="extURL" target="_blank">kalle</a></span>. it is under heavy construction. all conventions made here are only suggestions and can of course be discussed. i'm looking forward to your contributions!**  

you may download lots of modules at **[kalle.Modules.DMX](xref:)**  



#  Modules for intelligent DMXequipment
For working with intelligent lighting equipment it is useful to have some special modules.  

* **driver-nodes for DMXinterfaces**  
*naming proposal:*|**DMX (Devices**manufacturer**)**  
--- | ---  
*example:*|**DMX (Devices**DMX4all**)**  
---  
* **DMXfixtures**  
---  
These Modules combine all Parameters of a MovingLight to a spread which can be sent directly to DMXinterfaces or to DMXsimulations.  
*naming proposal:*|**DMX (Devices**manufacturer**)**  
--- | ---  
*example:*|**DMX (Devices**DMX4all**)**  

* **DMXsimulation**  

These modules should simulate a MovingLight in a 3D-rendering environment.  
These Modules should have a spreadable transform input for placing them in the 3Denvironment  
These Modules should have a spread input which can be fed directly from the corresponding **DMXfixture**-module.   
*naming proposal:*|**DMX (Devices**manufacturer**)**  
--- | ---  
*example:*|**DMX (Devices**DMX4all**)**  
---  
* **DMXspreads**  
---  
These modules should generate useful spreads e.g. for chasing etc.  
*naming proposal:*|**DMX (Devices**manufacturer**)**  
--- | ---  
*example:*|**DMX (Devices**DMX4all**)**  

* **PanTilt**  
These modules should generate special which are especially useful for controling the head-(*or mirror*) movement of several MovingLights  
*naming proposal:*|**DMX (Devices**manufacturer**)**  
--- | ---  
*example:*|**DMX (Devices**DMX4all**)**  
---  
* **GenericDMX**  
---  
Everything else for generic DMX usage  
*naming proposal:*|**DMX (Devices**manufacturer**)**  
--- | ---  
*example:*|**DMX (Devices**DMX4all**)**  

The advantage is that all "DMX"-Modules appear near by near in the 'categorized nodelist'.   

You have several Categories (DMXfixture, DMXsimulation and DMX for generic Helpers) to choose from.  
![](~/img/dmxfixtures.jpg "")  

![](~/img/dmxtutorial.jpg "")  

**variable**/**fix**  







##  DMXfixtures Modules
>should combine all functions of a DMX Fixture to a spread that can be directly sent to a DMXinterface.  

Let's have a look at a typical module for a moving light:  
the <a href="http://www.glp.de/de/Produkte/Spiegelbewegte_Lichtsysteme/pocket-scan.html" class="extURL" target="_blank">Pocketscan</a> from <a href="http://www.glp.de" class="extURL" target="_blank">GLP</a> is a very cheap movinglight (less than 300 Euro !) controlled via DMX.  
It uses 7 DMXchannels and has as a special gimmick a laser pointer inside.  

![](~/img/glppocketscandmxdevices_2007.01.1816.10.59.jpg "")  

With that *Resample/Swapdim/count of devices*thing inside the pocketscan module seen above you may control parameters for all units simultaneous by simply changing a value or you may benefit from vvvv's technology called Spreads.  
Put a Spread with a whatever slicecount onto any of the Inputpins of that pocketscan module - that *Resample (Spreads)* node in *Repeat Mode* prevents any collapsing.  

A simple *Cons (Spreads)* combines that spreads together and feeds one of vvvv's various DMXnodes.  

Note that there are other movinglights with a little more features. The <a href="http://www.vari-lite.com/index.php?submenu=3000Spot&src=gendocs&link=Prod_3000S_Intro&category=Main" class="extURL" target="_blank">Vari-Lite VL3000 Spot</a> e.g. uses 28 DMXchannels and costs a little less than 10.000 Euros.   
See that module below?   
29 Inlets and 140 nodes inside...
 *naming proposal:*|**DMX (Devices**manufacturer**)**
--- | ---  
*example:*|**DMX (Devices**DMX4all**)**  

## DMXsimulation Modules
>DMX Fixture Simulation Modules should have a DMXspread Input and a Layer Output  
![](~/img/mac300sim.jpg "")  

---  




##  Pan/Tilt Movement Modules
![](~/img/circshaper.jpg "")  

##  DMX General Purpose Modules
16bit split
16bit join
AsValue (DMX)  
AsDMX (Value)  
StartAdress (DMX Boolean)  
