---
uid: aab49eac-b551-4c7b-81f4-09f6f0f48176
---

# WebBased Configuration Interface
**under construction**  



# Welcome

on this site you will find some informations about Webbased Configguration Interface  


# Introduction

The Webinterface gives the VVVV Users the possibility to create Webpages based on HTML, CSS and Javascript (JQuery) and communicate over Http between a browser and VVVV.  
For Informations how to use the Webinterface see the Manual Page.   


# Download & Requirements

(Filelink)  

Requirements:  
* [VVVV  > beta21](https://vvvv.org/downloads)
* <a href="http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=0856eacb-4362-4b0d-8edd-aab15c5e04f5" class="extURL" target="_blank">.Net Framework 2.0</a>  
* Webinterface.dll  

Install:  
Just unpack the File to the VVVV Plugin Folder.   


# Roadmap

## Framework
* Expand HTTP GUI base class| Have a output pin that spits out all post data as raw xml | Add output pins for ID and class  
* Rewrite the Saving mechanism with all the new raw data  
* Deleting WebinterfaceSingelton if all Nodes s are deleted  
* Switching to jQuery 1.4  


## Server
* Standardized communication protocol  
* Polling / Comet Communication   

## Node Changes
* Rewrite existing javascript generation with our new library (Button, Slider, Textfield)  
* CSS Rule node  

## New Nodes
* File Upload / Pool  
* Image (DynamicImage (Streaming); SVG embed)  
* Combobox (Dropdown)  
* Button (grafik)  
* Tabboxen  
* Splitpanes  
* Html Tables  
* XML Page (oder Pins an der HTML page)  
* Abstraktes XML Tag  
* Datepicker  
* Accordoin  
* Dialog  
* Resizable  



## Documentation
* How to use wiki page  
* XML Comment Source Code  
* How to write my own Http Node  
* Complete Helppatches  

# Nodelist
## HTTP

Renderer (Http)  

**Config Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  




**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


**Output Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Page  

**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


**Output Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


---  


## GUI

BaseNode  

**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


**Output Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Button  

**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  
---  
**Output Pins**  
Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount||  


Button(Texture)  

**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


**Output Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Checkbox  

**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


**Output Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Colorpicker  

**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


**Output Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Container  



Group  

**Config Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


**Output Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Image  

**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Link  

**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Radiobutton  

**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


**Output Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Slider  

**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


**Output Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Text  

**Input Pins**  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  


Textfield  

_Input Pins** 

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



**Output Pins** 

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



---  
## CSS

Background  

**Input Pins** 

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Border  

**Input Pins** 

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  





Property  

**Input Pins** 

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  





Font  

**Input Pins** 

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  





Padding  

**Input Pins** 

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  





---  


## JQuery
Attr  

**Input Pins** 

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Css  

**Input Pins** 

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  




Draggable  

**Input Pins** 

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  



Droppable  

**Input Pins__  

Name| Description | Type |   
--- | --- | --- | ---  
Port|  
--- | --- | --- | ---  
Pagecount|  




---  



# Change Log
Initial Release  


# Relatet Links
[WebBasedConfigurationInterface TheTask](xref:5e45a523-716b-4469-abd5-e0205cd36ecb)  
[http://jquery.com/]  
[http://jqueryui.com/]  
[http://jqueryui.com/themeroller/]  
[http://www.eyecon.ro/colorpicker/]  
[http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=0856eacb-4362-4b0d-8edd-aab15c5e04f5]  



###  Question 


Send an PM to Phlegma or contact me with Skype (nils.buhlert)  



###  Credits 


Josh Samberg  
Christain Moldenhauer  
vvvv Group  
Meso  

