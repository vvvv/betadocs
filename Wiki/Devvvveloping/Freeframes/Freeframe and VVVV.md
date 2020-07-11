---
uid: 4b398d22-e01e-44f7-bd95-678ced634860
---

# Freeframe and VVVV
## About FreeFrame
The official source for information about freeframe is its hompage at:  
<a href="http://www.freeframe.org" class="extURL" target="_blank">http://www.freeframe.org</a> 

FreeFrame is a specification of how you have to write a videoplugin so that it can be used in a large number of applications. It is designed to be crossplatform and independent of a programming language. Therefore plugins can be written in any language as long as the result is a .dll (for windows, and something else for linux and osx).  

## FreeFrame and vvvv
vvvvs videoplayback is based on microsofts directshow. for a freeframe.dll to be used in a directshow graph vvvv comes with a filter (<a href="http://sourceforge.net/project/showfiles.php?group_id=66712&package_id=105856" class="extURL" target="_blank">DSFreeFrameWrapper.ax</a>) which is a wrapper around freeframe.dlls that makes them look like an ordinary directshowfilter to a graph. this is the same idea as having a filter that wraps vst-plugins to dxi-instruments.  

Actually this is not important for you who just wants to write a freeframe video effect since this wrapping is completely handled by vvvv. If you have a freeframe.dll just drop it on a patch to create a node (or put it in the /freeframe folder for it to show up in the nodelist).  


## Write your own plugins
There is a stepbystep guide to [writing freeframe plugins](TODO INTERNALLINK:writing freeframe plugins) available which is the documentation of the freeframe workshop held during node08.  

Also the freeframe sourceforge site offers sample code for writing plugins in VisualStudio and Delphi:  
<a href="http://sourceforge.net/projects/freeframe" class="extURL" target="_blank">http://sourceforge.net/projects/freeframe</a> 

## Extended FreeFrame Specification
The current freeframe specification has two shortcommings: You cannot have spreaded inputs and you cannot have outputs. Therefore the official freeframe specification has been extended to allow us having both. Bear in mind that those additions are not official. Version 2.0 of the freeframe specification is supposed to include something like this but its not yet sure if the extensions proposed here will make it into the specification. Anyway it is not that dramatic. For now those plugins will run within vvvv and later it will probably not be very hard to upgrade plugins to the final specification.  

Basically all you need to make use of the extensions is the two modified files FreeFrame.h and FreeFrame.cpp which you can find in any download of a sample plugin from the FreeFrame page.  

A complete listing of all the extensions is available on [Freeframe 1.0 Extended FreeFrame Specification](TODO INTERNALLINK:FreeFrameExtendedSpecification)  


## Freeframe and OpenCV
When writing your own freeframe.dll you have access to all the pixels of the videostream. At this point you are not limited to writing your own code but you can also include other image analysis/manipulation libraries that do the job for you. <a href="http://groups.yahoo.com/group/OpenCV" class="extURL" target="_blank">OpenCV</a> is one such library which has its focus on computer vision (i.e. tracking, ..) and can easily be used within a freeframe.dll.   

Find the sources of plugins that use OpenCV and ship with vvvv here:  
<span class="node">Contour (Freeframe DShow9)</span>  
<span class="node">CamShiftTracker (Freeframe DShow9)</span>  
<span class="node">ColorTracker (Freeframe DShow9)</span>  
<span class="node">Trautner (Freeframe DShow9)</span>