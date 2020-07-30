---
uid: e7a8f251-cdbc-459a-b249-2918654c9174
---

# Propaganda


Depending on where you come from you can approach vvvv in different ways. The following provides an overview of vvvvs main capabilities and features conveniently grouped by buzzwords.  


**vvvv is your favorite multipurpose toolkit.**   
**It is a hybrid visual/textual development environment.**  
**Free for non-commercial use.**  
**Commercial use requires a [license](https://store.vvvv.org/).**  



## Hybrid Visual/Textual Development Environment
![](~/img/vvvv_Propaganda_NEU_00_1.png "")   

  

 

Above all vvvv is targeted at the lazy developer and offers four things in one:  
* a topnotch development environment  
* a nextgeneration visual programming language   
* an extensive node/code library  
* a runtime environment  
Besides its own visual language, the environment is also host to our new visual language [VL](xref:89e664e5-1274-4966-a7cd-82255eea4483) and the two textual languages <a href="http://en.wikipedia.org/wiki/High-level_shader_language" class="extURL" target="_blank">hlsl</a> and <a href="http://en.wikipedia.org/wiki/C_Sharp_%28programming_language%29" class="extURL" target="_blank">c#</a>.  

Regardless of the language used, vvvv knows only one mode: *runtime*. Thus turning the notion of *stopping a program to recompile it* into a footnote of the early days of programming. Where necessary compilation happens behind the scenes and doesn't interrupt your flow of work.  

Extending vvvv with your own nodes is a breeze, see [developing plugins](xref:59d087cb-4622-4fda-9ed9-4b50b34dd573). In fact many parts of vvvvs node library are contributed by users via the addonpack and [Contributions](https://vvvv.org/contributions).  

---

## 2D/3D Animation
![dottore: Partitura #000](~/img/3d_1.png "dottore: Partitura #000")  
Interactive realtime 2d/3d animated cyber particles. vvvv has it all. Featuring 3 distinct fully blown industry standard rendering engines   
SVG, DirectX9 and DirectX11* vvvv leaves no eyes dry. Load/animate/generate 3D models and apply textures/shaders/lightning to your liking. A built-in timeline and the worlds smoothest filters animate your creations over time. Top that with topofthepops physics engines Box2D/Bullet* and you be the next multimedia rockgod.   

Entry points:  
[Documentation on Graphics](xref:853423af-e6ba-4908-935b-5154fd0e3f3f)  
[Documentation on Animation](xref:cfc19801-b2d5-438f-a7f6-0b40e128a236)  

---

## Multiscreen Setups
![TAMSCHICK: IFA Berlin 2012](~/img/boygroup_1.png "TAMSCHICK: IFA Berlin 2012")  
Designed from the ground up to handle massive multiprojection installations vvvv drastically lightens the effort involved in such setups. Using a technique dubbed boygrouping™ you can make a cluster of client PCs render to the beat of a server PC and distribute content to them n'sync. Synchronized video playback, softedge, warping and blending are all just limited by your imagination.   

Entry points:  
[boygroup](xref:9d029794-1266-4e60-961f-33e6f95af7e6)  

---

## Motion Graphics
![unc: TextureFX](~/img/motiongraphics_0.png "unc: TextureFX")  
Loving the likes of Photoshop and AfterEffects but loathing their rendering times and lack of interactivity? vvvv is just for you. With its plethora of professional grade texture effects* and a timeline that has no rival you shop your compositions at any resolution. In realtime.   

Entry points:  
<a href="https://vvvv.org/contribution/video-effects-and-compositing-tutorials" class="extURL contribution" target="_blank">Video effects and Compositing Tutorial</a>  
[Documentation on Animation](xref:cfc19801-b2d5-438f-a7f6-0b40e128a236)  

---

## Projection Mapping
![Michael Höpfel: Lightstrive](~/img/mapping_0.png "Michael Höpfel: Lightstrive")   
Need to project on an irregular surface while preserving the intrinsic shape of your content? By providing tools that let you load/create meshes resembling your projection surface and ways to place textures on them vvvv is extremely versatile when it comes to the needs of any projectionist.   

Entry points:  
[Projection Mapping Primer](xref:d09ac451-f613-447d-afaa-5a32cdc1ce8c)  
<a href="https://vvvv.org/contributions/1353+1351+2439+1352+7934+2438+1354+1355/2104" class="extURL" target="_blank">Projection Mapping Contributions</a>  

---

## Data Visualisation
![tekcor: Human Genome](~/img/dataviz_0.png "tekcor: Human Genome")  
Need to get a better view on endless lists of data? vvvv is a pro in helping you do just that. Read from disk, database (MySQL, PostgreSQL/SQLite/SQL/Odbc/OleDb*) or the network (HTTP, UDP,..), parse (xml, json, csv, regexpr,...), transform and draw (SVG, DirectX) large amounts of data with just a few clicks. Export your visualisations as vector graphics, still images, movies or just lists of even more data. With its paradigm called spreads™ vvvv makes it a childs play to handle large amounts of data.   

Entry points:  
[Documentation on Spreads](xref:00327d1e-65ba-4424-997d-615d9a469503)  
<a href="https://vvvv.org/contribution/parasitic-design-a-vvvv-beginners-cookbook" class="extURL contribution" target="_blank">Parasitic Design Tutorials</a>  

---

## Physical Computing
![Prototyping Interfaces](~/img/physical_0.png "Prototyping Interfaces")   
Wii*, Leap, Kinect*, Oculus Rift*, Arduino*,... vvvv does them all. And even more by offering readers/writers for most common standard protocols like MIDI, OSC, TUIO, DMX, HTTP, TCP, UDP to name only the hottest. Plug and Play at its finest. And also multitouch.   

Entry points:  
book: http://prototypinginterfaces.com  
[Documentation on Inputs and Outputs](xref:dc061415-349d-405b-9df8-03c10b60aa30)  

---

## Sound
![](~/img/sound.png "")   
Multichannel audio playback, FFT analysis, ASIO and whatnot. While vvvvs audiocapabilities can not compete with the likes of <a href="http://puredata.info/" class="extURL" target="_blank">PD</a> and <a href="http://cycling74.com/max" class="extURL" target="_blank">MaxMSP</a> it covers a wide range of applications that you'll come across in your daily multimedia needs.   

Entry points:  
[Documentation on Audio](xref:0308fa48-014f-4c08-8618-fe047611a3c6)  

---

## Computer Vision
![](~/img/vision_0.png "")    
Motion and face detection, color, blob, face and skeleton tracking, gesture recognition... you choose. With easy access to devices like the Kinect* and the Leap and libraries like OpenCV* vvvv is your perfect companion when it comes to quickly prototyping computer vision applications.   

Entry points:  
<a href="https://vvvv.org/contribution/vvvv.packs.image" class="extURL contribution" target="_blank">The Image Pack</a>  
[video](xref:7712d732-0b2e-4a27-bfb3-ef02f85f0794)  


---  
\* several parts of vvvvs node/code library are user contributed:   
<span class="user"><a href="https://vvvv.org/users/vux" class="extURL" target="_blank">vux</a></span>: DirectX11 (via DX11 pack), Box2d, Bullet, Bass, PostgreSQL, SQLite, SQL, Odbc, OleDb (via addonpack)  
<span class="user"><a href="https://vvvv.org/users/elliotwoods" class="extURL" target="_blank">elliotwoods</a></span>: OpenCV (via ImagePack)  
<span class="user"><a href="https://vvvv.org/users/unc" class="extURL" target="_blank">unc</a></span>, <span class="user"><a href="https://vvvv.org/users/lecloneur" class="extURL" target="_blank">lecloneur</a></span>: texture effects (via addonpack)  
<span class="user"><a href="https://vvvv.org/users/woei" class="extURL" target="_blank">woei</a></span>: advanced spread operations (via addonpack), GPU splines (via contributions)  
<span class="user"><a href="https://vvvv.org/users/dottore" class="extURL" target="_blank">dottore</a></span>: MRE - Multipass Render Engine (via contributions)  
These are only the biggest contributors, many more are contributing smaller bits.   

---  

You might also want to check the <a href="https://vvvv.org/blog/24" class="extURL blog" target="_blank">Galleria</a> to get an impression of what people do with vvvv. 