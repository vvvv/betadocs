---
uid: c518462e-bca3-48d5-98fd-2113adf5789e
---

# Abstract
All Beginner’s Workshops run for two full days and require no previous  
knowledge. After introducing the user interface of vvvv and it’s  
paradigms of a visual, node based programming language, you’ll learn  
to create various “essential” patches from scratch.   

# Requirements
Being able to install vvvv  

# Hosts
Group A (english): <span class="user"><a href="https://vvvv.org/users/MrBenefit" class="extURL" target="_blank">MrBenefit</a></span>   
Group B (german): <span class="user"><a href="https://vvvv.org/users/kathi" class="extURL" target="_blank">kathi</a></span>  

# Main Topics
These essential patches cover basic topics like:  
* Interface objects (color, string, enumerations, button, slider)  
* DX9 basic elements (Renderer, Quad, Grid, FileTexture)  
* Transformation (Rotate, Translate, Transform)  
* Spreads concept (LinearSpread, RandomSpread, Stallone, Queue)  
* Animation (LFO, Damper, Oscillator, DeNiro)  
* Subpatching (build your own nodes)  
* Transformation hierarchy (Rotate, Translate, Transform)  
* Camera animation and navigation (LookAt, Perspective)  
* Shaders (Phong, Gouraud, Constant, Tiki user shaders)  
* Meshes (Mesh, Sphere, Cylinder)  
* Video input (VideoIn, FileStream, VideoTexture)  
* Rendering/Exporting your animations (Renderer, MainLoop, Writer, Writer(NRT))  

<a href="http://vvvv.org/tiki-list_file_gallery.php?galleryId=36" class="extURL" target="_blank">Resources</a>  

# Walkthrough Topics and Resources

## 1. basics I
* welcome round and introducing ourselves  
* niveau check of participators  
* may i introduce to you: „vvvv“ + what is this and what can i do with it  
* relativisation (vvvv is not made to solve every task)   
* advice: vvvv.org + tiki + bulletin board. community and culture.  
* initiation in to the GUI and some specials of VVVV  
  * interface objects = IO box (Color, String, Enumerations, Button, Slider)  
  * herr inspektor (hidden pins)  
  * node categories  
  * patching style (comment, topdown, loops, input/output pins)  
  * important hotkeys  

**files group A (en) <a href="http://vvvv.org/tiki-download_file.php?fileId=1589" class="extURL" target="_blank">01 basics I.zip (142.73 Kb)</a>**  

## 2. basics II
* Hello World: DX9 basic elements (Renderer, Quad, FileTexture) and Primitives (Quad, Sphere ...).   
* coordinate System (AspectRatio)  
* transformation (Rotate, Translate, Transform)  
* spreads concept (LinearSpread, RandomSpread, TypoSpread, Stallone, Queue)  
* animation (Lfo, Damper, Oscillator, DeNiro, switch)  
* **task copy render window:** we give the target (Render Window). participators have to build up the patch by theirselves  

**files group A (en) <a href="http://vvvv.org/tiki-download_file.php?fileId=1590" class="extURL" target="_blank">02 basics II.zip (769.43 Kb)</a>**  

## 3. basics III
* subpatching (build your own nodes)  
* transformation hierarchy (Rotate, Translate, Transform(3D), Perspective)  
* **task copy render window:** solarsystem or other hierarchical animation  

**files group A (en) <a href="http://vvvv.org/tiki-download_file.php?fileId=1592" class="extURL" target="_blank">03 basics III.zip (427.48 Kb)</a>**  

## 4. 3d und Camera
* geometry/apply shader nodes, short introduction  
  * meshes = EX9.Geometry (xfile, sphere, cylinder) hinweis: cinema4d  
  * shading = EX9.Effect, shaders (Phong, Gouraud, Constant ...)  
* coordinatesystems: polar (= pitch yaw length) vs. cartesian (= x y z)  
* camera, analogy to reality (Dolly, Zoom, Perspektive, Far- und Nearplane)  
* camera transformation (Lookat, Transform(3D), Perspective)  
* **task copy render window:** build your own camera animation/navigation  

**files group A (en) <a href="http://vvvv.org/tiki-download_file.php?fileId=1593" class="extURL" target="_blank">04 3d + camera.zip (5.85 Mb)</a>**  

## 5. input and output
* mouse  
* keyboard  
* sound (FFT, BeatDetection)  
* webcam (VideoIn)  
* play videos (FileStream, VideoTexture, Blend)  

* file export images/video (Renderer, MainLoop, Writer, Writer NRT)  
* presenting working with multi rendering setups  

## 6. helpful nodestructures
spreads  
* getSlice/setSlice  
* sorting  
* stallone  
* binSize  
* cons  
* i  
* cross  
* resample  

if  
* switch  
* counter  
* select  
* boolean operators  

feedback  
* framedelay  
* s+h  

diverse  
* map  
* Bounds  
* stopWatch  
* Renderer TTY  

((westtricks|WestTricks))