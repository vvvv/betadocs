---
uid: 772e8696-25d4-4d8b-a31b-db4dd1ce1f3f
---

# Using Addons

When downloading vvvv it comes with a large library of native/built-in nodes ready to be used.   

Additionally many users have created and are sharing [addons](xref:e1161303-b566-408c-86f2-1cf6cb8137b7) in 3 different ways. Here is how to use them.  

After "installing" an addon you have access to all its nodes via the [Node Browser](xref:eeb8526d-0085-4219-a138-32ac397853f1) among all the native nodes.   



>note:  
For unpacking any download we recommend using <a href="http://www.7-zip.org/" class="extURL" target="_blank">7zip</a> since many users had problems with other unpackers (including the built-in windows function).  
  



# The Addonpack

![](~/img/Addons_Addonpack2.png "")   


The Addonpack is a highly recommended collection of useful nodes provided and maintained by members of the vvvv community.   

[Download](https://vvvv.org/downloads) the Addonpack matching the exact version of vvvv you're using. Then unzip and place it inside the vvvv directory so your directory structure looks like this:  

 \addonpack\ (including: girlpower, lib,...)
 \girlpower
 \lib
 \licenses
 \vvvv.exe
 ...


# Other Packs

![](~/img/Addons_Packs.png "")   


<a href="https://vvvv.org/contributions/7934/all" class="extURL" target="_blank">Packs</a> are topical collections of plugins provided by the community.   

Any pack (apart from the Addonpack) has to be placed inside a directory called \packs so that your directory structure will look like this:  

 \addonpack 
 \girlpower
 \lib
 \licenses
 \packs\ (including \DX11, ..)
 \vvvv.exe


# Contributions

![](~/img/Addons_Contribs.png "")   




[/Contributions](https://vvvv.org/Contributions) are a simple way for anyone to share modules, effects, plugins...   

If you want to use any contribution you downloaded you best do it like this:  
* create a directory anywhere called e.g. "vvvvContributions"  
* in that directory create 3 directories called: \effects, \modules and \plugins   
* unzip the downloaded contributions in those respective directories (ie. effects into the \effects directory, plugins into the \plugins directory)  
* in vvvv open the root patch (by pressing <span class="keyseq"><kbd>ALT</kbd><kbd>R</kbd></span>)  
* in the root patch follow the instructions to add the path to your "vvvvContributions" directory.   

The good thing now is that you can share this collection of contributions between different versions of vvvv. So when you start using a new version of vvvv you only need to reference that directory of your contribution-collection in the root.   
>note:  
Some contributions may fail to work with newer versions of vvvv. In that case you'll have to see if a new version of this particular contributions is available.  
  


# DX11 Effects


The DX11 Pack uses several shader types, so packs & contributions that are DX11 based can have additional folders next to the effects folder (which is DX9 only):  
* "dx11" folder containing normal dx11 shaders: ***.fx** files  
* "geom11" folder containing dx11 geometry shaders: ***.gsfx** files  
* "texture11" folder containing dx11 texture FX shaders: ***.tfx** files  
