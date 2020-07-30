---
uid: 5a860cda-6d80-4168-92b1-5d5bbc50838a
---

# Tonfilm Modules
most modules are updated for current vvvversion, the old versions for beta8.1 are still in the [Modules Gallery](https://vvvv.org/tiki-list_file_gallery.php?galleryId=1)   

you should place all modules and help files into:  
**/modules/tonfilms**  



---  
#  Boygroup/Network

##  tonfilm-VideoSync

>note:  
this is old stuff, go here: [video synchronization](xref:75aad9ef-ba8c-4fa4-a846-03ae5fed5670)  
  

this module synchronizes videos with the same length on different computers in a boygroup setup. they will not be more than 2 frames out of sync if you are using a codec that can change playback speed in fine steps. open the file "VideoSync (VVVV Server).v4p" to see a basic setup. read [this forum thread](https://vvvv.org/tiki-view_forum_thread.php?comments_parentId=12591&topics_threshold=0&topics_offset=4&topics_sort_mode=lastPost_desc&topics_find=&forumId=7) for a little more info.  

[/tiki-download_file.php?fileId=943videosync.zip (7.03 Kb)](https://vvvv.org/tiki-download_file.php?fileId=943videosync.zip (7.03 Kb))  

---  
#  Transform

##  tonfilm-ShadowsOnPlane
with Shadow (Transform) you can project any 3D object into a plane, using light direction (or position).  
this is a simple method to generate shadows from 3D objects, but also limited. it works by projecting any input point on a given plane using a transformation matrix. open the heplfiles for examples.  

[ShadowsOnPlane.zip (33.55 Kb)](https://vvvv.org/tiki-download_file.php?fileId=591)  

contains five modules:  

all inputs spreadable, but a little slow sometimes:  

*ShadowPos (Transform OnPlane LightPosition).v4p*  
*ShadowDir (Transform OnPlane LightDirection).v4p*  

very fast but only the object input is spreadable, not the plane or light:  

*ShadowPos (Transform OnPlane LightPosition Simple).v4p*  
*ShadowDir (Transform OnPlane LightDirection Simple).v4p*  

and to project the shadows on, a plane is also included:  
*Plane (EX9.Geometry Vector Out).v4p*  

##  tonfilm-ObjectAxisRotation
this is a rotation always around the axis of the object. looks damn cool, try the help patch ... used in [kiilo - FlyingCamera](xref:3999690a-9bed-4fea-99f3-5cc8bb519587)  

[ObjectAxisRotation.zip (8.98 Kb)](https://vvvv.org/tiki-download_file.php?fileId=590)  
 
##  tonfilm-EgoShooter
the EgoShooter (Transform).v4p module, is like a camera. connect it to the projection pin of Renderer (DX9), and you will be able to move with some keys thru your vvvvorld in EgoShooter style (Rotation and forwards/backwards)  

[EgoShooter.zip (7.37 Kb)](https://vvvv.org/tiki-download_file.php?fileId=594)  

on this second version i added a very special feature:  
if you press r for reset to InitPos, Mr. DeNiro drives you smooth and  
securely home.  

![](~/img/egoshootertransformhelp0.jpg "")  

---  
#  DX9/EX9

##  tonfilm-QuadGrid
a grid geometry module to have quads instead of triangles in wireframe mode.  

[QuadGrid.zip (3.65 Kb)](https://vvvv.org/tiki-download_file.php?fileId=1063)  

 ![](~/img/vertexshadertransforms2directxrenderer0.jpg "")

##  tonfilm-VectorDX9
draw a line that represents the input vector, based on kalles Line (DX9)  

[VectorDX9.zip (9.05 Kb)](https://vvvv.org/tiki-download_file.php?fileId=593)  

---  
#  GDI

##  tonfilm-TransformGDI
make some simple 2d transform hierarchies:  

[Transform GDI.zip (4.37 Kb)](https://vvvv.org/tiki-download_file.php?fileId=753)  

![](~/img/transformgdihelp.jpg "")  

---  
#  3d

##  Angle3d
angle between two vectors output is 0 ... 0.5.  
multiply with 2*Pi to get radeans, with 360 to get degrees.  

[VectorAngle.zip (2.95 Kb)](https://vvvv.org/tiki-download_file.php?fileId=592)  

see [3d Vector Mathematics](xref:d7b17d70-42b3-4b01-8488-3406aef4f42f)  

![](~/img/angle3dvectorhelp.jpg "")  

---  
#  Value

##  tonfilm-MathConstants
this is based on [kalles idea](xref:) simply to store the values in IOboxes inside the module. but with <span class="node">IOBox (Value Advanced)</span> the values get rounded to 4 decimals, but it works with <span class="node">IOBox (String)</span> and <span class="node">AsValue (String)</span>.  

[MathConstants.zip (2.53 Kb)](https://vvvv.org/tiki-download_file.php?fileId=318)  

![](~/img/mathconstantsvaluestoredandsendhelp.jpg "")  

---  
#  Devices

##  tonfilm-MidiNotePlayed
this module listens to all midi notes of a channel, and outputs the played one as spread.  

[MidiNotePlayed.zip (3.54 Kb)](https://vvvv.org/tiki-download_file.php?fileId=503)  

##  tonfilm-VirusCMidi
have build this to use my access virus c with vvvv.  

i recommend to install the help patch also, to test every controller.  

Module:  
[VirusCMidi (Devices).v4p (36.05 Kb)](https://vvvv.org/tiki-download_file.php?fileId=31)  


Helpfile:  
[/tiki-download_file.php?fileId=30](https://vvvv.org/tiki-download_file.php?fileId=30)VirusCMidi (Devices) help.v4p (63.63 Kb)]  

.. and a picture of the helpfile:  
![](~/img/viruscmidideviceshelp1_3.jpg "")