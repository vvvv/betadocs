---
uid: 3999690a-9bed-4fea-99f3-5cc8bb519587
---

# Idea

i think having a flying camera would be fine in vvvv. It should have he following features:  

* independent rotating between 3 achses (quaternion rotation)  
* forward // backward   
* up // down  
* tonfilm completes: left // right (without any rotation)  
* using the cursor keys + <shift> ctrl  
* or joystick  

{picture file=img/wiki_up//rotation.jpg}  

# try & errors
i build the following patch to get i touch with quaternions ..  
* v0.2 [quaternion02.zip (4.12 Kb)](http://vvvv.org/tiki-download_file.php?fileId=202)  

object axis rotation using quaternions *by <span class="user"><a href="https://vvvv.org/users/tonfilm" class="extURL" target="_blank">tonfilm</a></span>*:  
* [ObjectAxisAlgorithm2.v4p (41.92 Kb)](http://vvvv.org/tiki-download_file.php?fileId=203)</a>  

![](~/img/objectaxisalgorithm0.jpg "")  

FlyingCam module by [UserPagetofilm|tf] + [UserPagekiilo|kiilo]  
* [flyingCam.zip (4.89 Kb)](http://vvvv.org/tiki-download_file.php?fileId=204)</a>  
simple Gamepad Version by [Userpagephl|phl]  
* [FlyingGamepadCam.v4p (53.84 Kb)](http://vvvv.org/tiki-download_file.php?fileId=945)</a>  

![](~/img/flyingcam.jpg "")  
# todo
* joystick  
* find a different reset point not (0, 0, 0)  
* store + recall of intressting points  

