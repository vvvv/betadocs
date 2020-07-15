---
uid: 3ac2ed1f-db6d-4f0f-8679-80183ab51517
---

# Export from 3D Modelling Software

##  Maya
See [How to Export X Files from Maya](xref:2db04338-b1c9-4922-aada-369b238caac1)  

## Cinema 4d
Cinema 4d offers built-in export for x-files, however vvvv had problems reading them (the mesh-output-pin said "nil"). Joreg mentioned <a href="http://213.239.195.198/~philipp/index.php" class="extURL" target="_blank">XPORT</a> (free), which offers an advanced dialogue and worked for me.   
V10+ seems to export fine however the scale is wrong, if you scale to 100 in the export dialogue things seems a bit closer to the right range.  
Collada files also work fine  

note from u7angel: cinema4D 11.5 direct3D export does not save UV coordinates. only XPORT works  

## Blender

See [elektromeier TutorialBlender](xref:d16da23f-30ae-4ffd-93be-88fd40e2534e)  

Probably the most complete free software for 3D modeling, Blender claims to have native X-File export. Anyone who's had experiences with that: please post it here.  

<a href="http://www.blender3d.org" class="extURL" target="_blank">blender web site</a>  

* A blender plugin for .xporting, <a href="http://development.mindfloaters.de/DirectX_Exporter_Mod.8.0.html" class="extURL" target="_blank">DirectX Exporter Mod</a> - claims that it produces "well formated and accurate DirectX-Files"  

* <a href="http://projects.blender.org/frs/?group_id=24&release_id=284" class="extURL" target="_blank">official DirectX Exporter</a> - personally i got better results with official directx exporter, especially since the above mentioned mod seems to be of an older date."  

* And the new blender version (2.40) offers "improved x-file export".  

## 3dsMax

There is a plugin for max <a href="http://www.andytather.co.uk/Panda/directxmax.aspx" class="extURL" target="_blank">Panda xfile exporter</a>  
I usually find scaling the mesh to between 1% and 5% brings its scale  in line with vvvv, otherwise its too big to see! Sometimes I have also had the nil pin as mentioned above, although I think it might be to do with mesh size!  

Another alternative exporter is <a href="http://www.kwxport.org" class="extURL" target="_blank">kW X-port</a>. I highly recommend this one to people having problems with Panda xfile exporter.  


## Google Sketchup
There is also a plugin for exporting Google sketchup foiles into x.files. <a href="http://jamesewelch.wordpress.com/2008/03/07/how-to-load-a-google-sketchup-model-into-a-xna-game/" class="extURL" target="_blank">You will find x.exporter for Sketchup here</a>. Just donwload and copy into plugin folder and it will be found in plugin tab.  
Other link: <a href="http://www.jamesewelch.com/2008/03/07/how-to-load-a-google-sketchup-model-into-a-xna-game/" class="extURL" target="_blank">link</a>  

TIP: This exporter is great for an easy and consistent way to get subsets in your X-Files. Just group whatever geometry you want as each subset and export. Sketchup orders the groups the order you created them or alphabetically. The exporter orders the subsets based on the group order so it's quite easy to manage what group end up as subset.  

More useful tools:  
* <a href="http://www.smustard.com/script/MoveToOriginAndCenter" class="extURL" target="_blank">MoveToOriginAndCenter</a> - Moves the entire selection to the axis origin, and places the models center at the origin. Great before exporting.  
* <a href="http://forums.sketchucation.com/viewtopic.php?t=22920" class="extURL" target="_blank">CleanUp</a> - optimize and clean up a model.  
* <a href="http://www.smustard.com/scripts/" class="extURL" target="_blank">Companion to SketchUpTM</a> - more useful tools.  

Google Sketchup Warehouse has a huge library with free models.  

Please also see the 3D Modelling section on the [Graphics Links](xref:667098f9-f169-458c-b7b5-2b283581fef0) page  


# X-file in general

If you have trouble to open your x-file - mesh output pin of xfile.node shows NIL - then best you check your x-file manually. Open it with Wordpad and look if you have (in this order):  
* Material { ... } data,  
* Mesh { ... } data, (you'll probably have)  
* MeshMaterialList { ... } data,  
* MeshTextureCoords { ... } data,  

One very rare problem could be, that your Frame name has a number in the beginning, in the end it isn't a problem.  

You can very easy combine your x-file into a nested x-file containing several modells with own world-origins by copying all data inside the Frame { ... } tag and adding it in your destination x-file. So, you can add Frame under Frame there.  
In VVVV you can switch between these modells by GetSlice.node or see all without former.  
(I just did this with one texture for all modells)  

##  Textures and UV Mapping

* When in need of proper UV mapping, be sure to place a texture on the Object in your 3d Tool before you export as X File. As long as there is no texture attached, the UV maps won't work properly in VVVV.  