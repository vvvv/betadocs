---
uid: d16da23f-30ae-4ffd-93be-88fd40e2534e
---

# Elektromeier TutorialBlender
On this page i will post some mini tutorials that show, how to prepare meshes in blender for optimal use with vvvv. Exporting .xfiles out of blender is quite tricky and needs some experimentation, the exporter seems to have some issues which i also dont understand entirely. But the most time when you got a corrupt mesh that gives you a nil output on the xfileloder, the reason are some bad characters in the naming of the materials/objects.  

also have a look on this thread:  
http://vvvv.org/tiki-view_forum_thread.php?forumId=7&comments_parentId=10895#threadId10935  


Now lets start with the first tutorial.  

# export a beveled text
this tutorial shows to create a beveled 3dtext, define each character as a subset and export as a .xfile ready for use with vvvv. after that you can handle each character as a slice in vvvv.  

first download and install the latest x file exporter from ben omari:  
http://xoomer.alice.it/glabro1/python.html  

the built in exporter in blender 2.42 seems to have some problems with exporting subsets.  

* create a text  
* change to object mode (hit TAB) to see the effects of extruding and bevelling.  
* convert it to a ordinary curve with alt-c  
* convert it to a ordinary mesh with alt-c again  
* go to edit mode and select the first character. make sure to disable the "Limit Selection To Visible" button to select the hidden vertices too. you can find this button in the viewportwindow, when editmode is active.  
* separate the selected character from the rest of the mesh. to do this select the menu "mesh". you can find it also in the viewport window. then go to vertices -> separate. or just use hit P on the keyboard (Shortcut to separate)  
* Do the last two steps for all the characters.  
* Now we have to assign a new material to each character. only this way the exporter handles the single meshes as subsets. Change to Object-Mode. select the first character. then open the shading panel by hitting F5. Make sure that the "ME" button is active and "OB" is disabled". Then hit "Add New" under the material section. you can enter a name for the material i f you like but dont use special characters like german "ä, ö, ü" etc. when giving material or groupnames in blender. this causes a corrupt .x file!  
* do the last step for each character.  
* Now were going to place each character to the center of the world. also all the origin axises of the character lie there becuase weve extracted them from one mesh. later in vvv we can use a linear spread with transform to lign them up again.  ok, for tdoing this go to the editing panel. you can get there by pressing <span class="keyseq"><kbd>F9</kbd></span>. then select the first character an press "Centre" und the "mesh" section.  
* do this for each character  
* export as an .x file. download the additional .x exporter by ben omari. the built in exporter doesnt seem to handle subsets.  
* import in vvvv with the "xfile" node.  

# Troubleshooting
* Be carefull when u use the "normals" node in vvvv, because this node messes around with the subsets. i spent hours with different blender settings because i thought its a blender issue...   
7.feb.2007: "normals" works correct now in beta 12!

* Make sure that each object have an material assigned like described above. if ou have one object in the file without assigned material, the .xfile becomes corrupt  

* also dont use special characters (like german "umlaute" for object or material names. if you do: guess what... corrupt .xfile  

>TIP: If you import some objects in other formats to blender, you often to change dozens of materialname because they can contain special character. doing this in blender can be very anoying. you can leave the names as they are, export the .x file, open it in your favorite editor and search an replace those special characters