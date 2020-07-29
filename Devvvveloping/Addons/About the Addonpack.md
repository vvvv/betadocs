---
uid: e1554948-8a15-4e39-8289-59216c388376
---

# The idea

[addons](xref:e1161303-b566-408c-86f2-1cf6cb8137b7) are shipping as a separate download in the form of addonpacks. They include the following types of contents:  

```
 \effects
 \freeframe
 \modules
 \plugins
```

There is at least one addonpack per vvvv release, possibly more, providing consistent collections of addons for specific releases. By naming the packages like:  
```
addonpack_betaXX_01.zip
```  
it will always be obvious which vvvv-release a specific pack is supposed to work with.  

# Download

The latest pack will always be available from the [Downloads](https://vvvv.org/downloads) page.   


# Installation

![](~/img/vvvv_folder_short-setup.png "")   

Simply unzip the addonpack to your \vvvv_45betaXX directory overwriting all files, if you are asked.   

note:  
Only use addonpacks with vvvv-releases that carry the same version number (ie. betaXX).  
   

There can be several addonpacks for one vvvv-release, numbered like addonpack_betaXX_01, ..._betaXX_02, ..._betaXX_NN.   
**Always use the latest available.**  



# Contributing

In order to contribute stuff to the addonpack please follow the instructions on the [vvvv sdk](xref:51377b2d-17a4-4b5f-b0c1-eb2cc11fe251) page. Essentially what you have to do is:  
* fork the public vvvv repository  
* add your code  
* send us a pull request.   

Depending on the type of addon there are also specific details:  
* [AddonPack.Effects](xref:557d6915-5069-483e-8175-2834225be56b)  
* [AddonPack.Modules](xref:be2a7b95-9a02-4bdf-8506-e10292de80f4)  
* [AddonPack.Plugins](xref:16491d30-9b16-48d5-8ad1-74ca43a2c1dd)  

