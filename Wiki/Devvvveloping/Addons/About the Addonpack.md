---
uid: e1554948-8a15-4e39-8289-59216c388376
---

# The idea

[Addons](TODO INTERNALLINK:About Addons) are shipping as a separate download in the form of addonpacks. They include the following types of contents:  

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

The latest pack will always be available from the [Downloads](TODO INTERNALLINK:Downloads) page.   


# Installation

![](~/img/vvvv_folder_short-setup.png "")   

Simply unzip the addonpack to your \vvvv_45betaXX directory overwriting all files, if you are asked.   

note:  
Only use addonpacks with vvvv-releases that carry the same version number (ie. betaXX).  
   

There can be several addonpacks for one vvvv-release, numbered like addonpack_betaXX_01, ..._betaXX_02, ..._betaXX_NN.   
**Always use the latest available.**  



# Contributing

In order to contribute stuff to the addonpack please follow the instructions on the [vvvv sdk](TODO INTERNALLINK:vvvv sdk) page. Essentially what you have to do is:  
* fork the public vvvv repository  
* add your code  
* send us a pull request.   

Depending on the type of addon there are also specific details:  
* [AddonPack.Effects](TODO INTERNALLINK:AddonPack.Effects)  
* [AddonPack.Modules](TODO INTERNALLINK:AddonPack.Modules)  
* [AddonPack.Plugins](TODO INTERNALLINK:AddonPack.Plugins)  

