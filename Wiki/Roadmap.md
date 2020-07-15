---
uid: 739fa4ab-925f-4379-9aea-857f76cef1f6
---

# Roadmap
By highlighting notable events along the road to creating a comfortable visual live-programming environment for everyone, this page provides a glimpse into the history of making vvvv. Further, we're giving an outline of future milestones to give you an idea where this is all heading...  

For more details on changes for individual releases please consult the full [Change Log](TODO INTERNALLINK:Change Log) and follow our <a href="https://vvvv.org/blog/1575+1576+23" class="extURL blog" target="_blank">Development Blog</a>.  
For a more colorful rendition of the same events see MESO's <a href="https://meso.design/en/articles/the-flow-of-creative-expression-paving-the-way-for-vvvv" class="extURL" target="_blank">vvvv history page</a>.  

# Upcoming Milestones
* vvvv beta40 including latest VL  
* finalization of depth camera libraries: Kinect v1, v2 and v3, Astra, Nuitrack, RealSense  
* finalization of networking libraries: UDP, OSC, TUIO, MQTT, ZMQ  
* preview release of <a href="https://www.youtube.com/playlist?list=PLBTgwgsWWcT9RFmWJ3kLOK-ota8k8YTph" class="extURL" target="_blank">VL.Stride</a>  

## Further on our agenda, to be reviewed after the vvvv gamma release:
(without claim of completeness and in no particular order)  
* Node Libraries  
  * 3d/VR/AR graphics and physics simulations using VL.Xenko  
  * Audio/Video playback using VL.GStreamer  
  * UI library  
  * Logging library  
  * 2d physics library  
  * Machine learning and AI  
  * More libraries (devices,..)  
* Deployment: OSX/Linux executables, mobile (iOS/Android), when available investigate deployment to Meadow and ultimately why not to the web.  
* Run editor on osx/linux  
* Improve Navigation (Browserlike, live object graph, multi-window support)  
* Integrating additional editors (Node Inspektor, Timelines, State machines, Curves, Meshes, ..)  
* AssetManager  
* Package management (create, deploy, consume packages)  
* Version control system support  
* Higherlevel language features  
* Better debugging support  
* Visual diff/merge  
* VL integration in other tools  

# vvvv gamma 
**2020.1** 01 04 20  
this is it: the first official <a href="https://vvvv.org/blog/vvvv-gamma-2020.1-release" class="extURL blog" target="_blank">stable release of vvvv gamma</a>. introducing also a new website: [http://visualprogramming.net]  

**2019.1-preview** 01 04 19  
marks the first (still low profile) <a href="https://vvvv.org/blog/vvvv-gamma-2019.1-preview" class="extURL blog" target="_blank">public release</a> of the previously introduced VL editor as a completely independent, standalone product. we therefore now distinguish between two products "vvvv beta" and "vvvv gamma" that are both hosting the VL editor.   

# vvvv 50: ~2016-dato
**beta35** 20 12 16   
adds new editor allowing to create dynamic plugins using VL and ships with the new <a href="https://vvvv.org/blog/introducing-the-editing-framework|Editing Framework)), new <a href="https://vvvv.org/blog/arduino-second-service|Arduino/Firmata nodes" class="extURL blog" target="_blank">arduino-second-service|Arduino/Firmata nodes</a> and new ((blog:how-tuio-do" class="extURL blog" target="_blank">TUIO nodes</a> patched in VL  

### Notable Series 50 events
Jannuary 2017: vvvv.org gets a <a href="https://vvvv.org/blog/introducing-the-store" class="extURL blog" target="_blank">Store for user contributions</a>  
May 2017: #vvvv opens on <a href="https://vvvv.org/blog/chat-vvvv-on-matrix.org" class="extURL blog" target="_blank">Matrix</a>  
NODE17: <a href="https://nodeforum.org/announcements/node17" class="extURL" target="_blank">5th edition</a> of the NODE Forum for Digital Arts with a 3h45min live-streamed <a href="https://www.youtube.com/watch?v=BKHbEWaHjcw" class="extURL" target="_blank">Keynode</a> featuring community achievements  
**beta36** improves DX9s way of handling <a href="https://vvvv.org/blog/aspect-ratio-and-projection-space|Aspect Ratio)), allows to <a href="https://vvvv.org/blog/vl-using-.net-libraries-and-writing-custom-nodes|use any .NET library directly in VL)), allows to [write to dynamic DX11 buffers from VL](TODO INTERNALLINK:blog:dynamic-dx11-buffers-in-vl), introduces an [Image Interchange Interface for VL" class="extURL blog" target="_blank">vl-using-.net-libraries-and-writing-custom-nodes|use any .NET library directly in VL](TODO INTERNALLINK:blog:vl-image-exchange-interface), allows to [write to dynamic DX11 buffers from VL](TODO INTERNALLINK:blog:dynamic-dx11-buffers-in-vl), introduces an ((blog:vl-image-exchange-interface|Image Interchange Interface for VL</a> and allows to ((blog:vl-one-frame-at-a-time" class="extURL blog" target="_blank">pause and step the execution of VL</a>  
March 2018: The first episode of <a href="https://www.youtube.com/channel/UCu-xqv-TLwv6L0An7MJJA5A" class="extURL" target="_blank">vvvvTv</a> airs, announcing <a href="https://vvvv.org/blog/vl-opencv-is-in-da-house" class="extURL blog" target="_blank">VL.OpenCV</a>  
May 2018: The <a href="https://discourse.vvvv.org/t/girlpower-folder/16357" class="extURL" target="_blank">Girlpower controversy</a>   
June 2018: The first [https://gettogether.community/vvvv/|vvvv Berlin meetup] takes place  
July 2018: First preview release of the 2d rendering engine <a href="https://vvvv.org/blog/VL.Skia" class="extURL blog" target="_blank">Skia for vl</a>  
August 2018: Work begins on the integration with the <a href="https://vvvv.org/blog/vl-threedee" class="extURL blog" target="_blank">Xenko 3d engine</a>  
**beta37** features an <a href="https://vvvv.org/blog/vl-corelib-cleanup|overhaul of VLs CoreLib)), introduces <a href="https://vvvv.org/blog/vl-groups-and-categories|Groups and Categories" class="extURL blog" target="_blank">vl-groups-and-categories|Groups and Categories</a> and allows to ((blog:vl-frame-your-patches" class="extURL blog" target="_blank">frame your patches</a>  

# vvvv 45: ~2010~2015
**beta24** 16 09 10  
introduces much simplified plugin-interface version 2 and adds a code-editor for live-coding c# plugins   

## Notable Series 45 events
**beta25** adds ProjectExplorer and Finder  
**beta25.1** introduces crack.exe  
November 2011 vvvv-sdk <a href="https://vvvv.org/blog/vvvv-sdk-on-github" class="extURL blog" target="_blank">is available on github</a>  
**beta26** ships with first massive series of TextureFX <a href="https://vvvv.org/blog/addons45beta2601" class="extURL blog" target="_blank">addons45beta2601</a>  
December 2011 introduces <a href="https://vvvv.org/blog/vvvv-ahead-of-time-builds" class="extURL blog" target="_blank">daily alpha builds</a>  
**beta28** introduces <a href="https://vvvv.org/blog/remoting-vvvv-exposing-pins-kontrolleur|Exposing IOBoxes)) and ((blog:cross-process-texture-sharing-depth-rendering" class="extURL blog" target="_blank">cross-process texture sharing</a>  
February 2012: the first <a href="https://vvvv.org/blog/prototyping-interfaces-interactive-sketches-with-vvvv" class="extURL blog" target="_blank">german vvvv book</a> is released  
December 2012: for its 10th birthday vvvv opens its <a href="https://vvvv.org/blog/vvvv-x|first international vlagshipstore)), is <a href="https://vimeo.com/56019214" class="extURL" target="_blank">celebrated by celebrities</a> around the world and massive contributor <span class="user"><a href="https://vvvv.org/users/vux" class="extURL" target="_blank">vux</a></span> announces his ((blog:everything-you-know..." class="extURL blog" target="_blank">DX11 contribution</a>   
**beta29** the 10 years anniversary release: adds <a href="https://vvvv.org/blog/vvvv-64bit|64 bit builds)), switches to <a href="https://vvvv.org/blog/vvvv-unicorn-upgrade|unicode)), adds the new [primitive datatype RAW](TODO INTERNALLINK:blog:new-datatype-raw) and introduces [HTMLTexture (EX9.Texture)" class="extURL blog" target="_blank">vvvv-unicorn-upgrade|unicode](TODO INTERNALLINK:blog:htmltexture-(ex9.texture)), adds the new [primitive datatype RAW](TODO INTERNALLINK:blog:new-datatype-raw) and introduces ((blog:htmltexture-(ex9.texture)|HTMLTexture (EX9.Texture)</a> and ((blog:player-(ex9.texture)" class="extURL blog" target="_blank">Player (EX9.Texture</a>)  
NODE13: <a href="https://nodeforum.org/activities/node-forum/node13/" class="extURL" target="_blank">3rd edition</a> of the NODE Forum for Digital Arts with first ever public demonstration of project "vvvv50", later to be named VL  
**beta31** adds <a href="https://vvvv.org/blog/protektor-dongle-protection-for-your-vvvv-projects" class="extURL blog" target="_blank">dongle-based protection</a> for patches  
April 2014: release of the <a href="https://vvvv.org/blog/50-the-humble-quad-bundle" class="extURL blog" target="_blank">Humble Quad Bundle</a>, a series of simple games patched with VL  
May 2014: the first <a href="https://vvvv.org/blog/vvvvook" class="extURL blog" target="_blank">japanese vvvvook</a> is released  
**beta32** gets rid of crack.exe after <a href="https://discourse.vvvv.org/t/please-rename-crack-exe-to-something-else/11440" class="extURL" target="_blank">crack-gate</a> and introduces <a href="https://vvvv.org/blog/refactor-to-subpatch" class="extURL blog" target="_blank">grouping of nodes</a>  
September 2014: A series of blogposts introduce vl, leading up to its initial release: <a href="https://vvvv.org/blog/50-that-next-big-thing.-an-overview.|One)), <a href="https://vvvv.org/blog/50-colors|Two)), [Three](TODO INTERNALLINK:blog:50-properties), [Four](TODO INTERNALLINK:blog:50-generics), [Five" class="extURL blog" target="_blank">50-colors|Two](TODO INTERNALLINK:blog:50-custom-datatypes), [Three](TODO INTERNALLINK:blog:50-properties), [Four](TODO INTERNALLINK:blog:50-generics), ((blog:50-custom-datatypes|Five</a>, ((blog:50-pre-release-roundup" class="extURL blog" target="_blank">Six</a>  
NODE15: <a href="https://nodeforum.org/activities/node-forum/node15/" class="extURL" target="_blank">4th edition</a> of the NODE Forum for Digital Arts with the first ever public workshops teaching VL and the Keynode (megashow) <a href="https://vimeo.com/129211880" class="extURL" target="_blank">Part 1</a>, <a href="https://vimeo.com/129085756" class="extURL" target="_blank">Part 2</a>  
May 2015: alpha builds are now <a href="https://vvvv.org/blog/vvvv50-vl-pack-alpha" class="extURL blog" target="_blank">shipping with VL</a>  
September 2015: A series of blog-posts follow the development of VL over the coming months: <a href="https://vvvv.org/blog/vl-summer-update|One)), <a href="https://vvvv.org/blog/vl-autumn-update|Two)), [Three](TODO INTERNALLINK:blog:vl-winter-update), [Four](TODO INTERNALLINK:blog:vl-spring-update), [Five](TODO INTERNALLINK:blog:vl-midsummer-nights-dream), [Six](TODO INTERNALLINK:blog:vl-progress-report-1), [Seven](TODO INTERNALLINK:blog:vl-progress-report-2), [Eight" class="extURL blog" target="_blank">vl-autumn-update|Two](TODO INTERNALLINK:blog:vl-progress-report-3), [Three](TODO INTERNALLINK:blog:vl-winter-update), [Four](TODO INTERNALLINK:blog:vl-spring-update), [Five](TODO INTERNALLINK:blog:vl-midsummer-nights-dream), [Six](TODO INTERNALLINK:blog:vl-progress-report-1), [Seven](TODO INTERNALLINK:blog:vl-progress-report-2), ((blog:vl-progress-report-3|Eight</a>, ((blog:vl-progress-report-4" class="extURL blog" target="_blank">Nine</a>  
**beta34.2** final release for WindowsXP  
October 2016: vvvv.org gets a <a href="https://vvvv.org/blog/forum.-new" class="extURL blog" target="_blank">new forum</a>  


# vvvv 40: ~2008~2010
**beta16** 08 04 2008  
adds a c# plugin-interface allowing thirdparties to contribute nodes  

### Notable Series 40 events
NODE08: First edition of the <a href="https://nodeforum.org/activities/node-forum/node08/" class="extURL" target="_blank">NODE Forum for Digital Arts</a> takes place in Frankfurt as the first vvvv user community meeting with <a href="https://vimeo.com/63157880" class="extURL" target="_blank">an introduction to the early years of vvvv</a>  
**beta18** releases first contributions by <span class="user"><a href="https://vvvv.org/users/elias" class="extURL" target="_blank">elias</a></span> as a vvvv intern: set-theory nodes, improved Expr node    
**beta19** comes with first <a href="https://vvvv.org/blog/addons40beta1901" class="extURL blog" target="_blank">Addonpack</a>   
**beta20** plugin interface now supports arbitrary types  
**beta22** introduces [multi-boygrouping](TODO INTERNALLINK:multiboygrouping)  
July 2010: big update to the <a href="https://vvvv.org/blog/new-vvebsite" class="extURL blog" target="_blank">website</a>  
NODE10: <a href="https://nodeforum.org/activities/node-forum/node10/NODE10" class="extURL" target="_blank">2nd edition</a> of the NODE Forum for Digital Arts   
December 2010: release of the first <a href="https://vimeo.com/18053849" class="extURL" target="_blank">vvvv commercial</a>  

# vvvv 33: ~2003~2008
**beta1** 24 12 02  
initial public offering  

### Notable Series 33 events
February 2003: <a href="https://pastwebsites.transmediale.de/03/de/03/scheduledetail.php?id=21&filtername=Workshop&filter=2&layerlayer=3_7_VIS#" class="extURL" target="_blank">first public workshop</a> at transmediale in berlin  
**beta5** switch from DirectX8 to DirectX9 rendering  
**beta6** added support for <a href="http://freeframe.sourceforge.net/" class="extURL" target="_blank">freeframe</a> plugins  
**beta7.4** added support for live-shader coding  
First license sold for non-MESO project to <span class="user"><a href="https://vvvv.org/users/elektromeier" class="extURL" target="_blank">elektromeier</a></span>  
**beta8** added 3d physics engine <a href="https://www.ode.org/" class="extURL" target="_blank">ODE</a>, needed for <a href="http://www.hoepfel.net/?page_id=29" class="extURL" target="_blank">Lightstrive</a>  
Jannuary 2005: release of <a href="http://web.archive.org/web/20050205214212/http://vvvv.meso.net:80/tiki-index.php" class="extURL" target="_blank">first wiki-based website</a>  
Jannuary 2006: vvvv leaves MESO and is now run as an independent company by <span class="user"><a href="https://vvvv.org/users/gregsn" class="extURL" target="_blank">gregsn</a></span> and <span class="user"><a href="https://vvvv.org/users/joreg" class="extURL" target="_blank">joreg</a></span>  
June 2006: <a href="https://vvvv.org/blog/website-relaunch" class="extURL blog" target="_blank">website relaunch</a> looked <a href="http://web.archive.org/web/20061118180717/vvvv.org/tiki-index.php" class="extURL" target="_blank">like this</a>  
**beta14** comes with first release of [TimelinerSA](TODO INTERNALLINK:TimelinerSA)  

# vvvv 32: ~2002
* most notably added Subpatches and Undo  
* prepared public release  
* <a href="http://web.archive.org/web/20021101213348/http://vvvv.meso.net/" class="extURL" target="_blank">initial vvvv website</a> on vvvv.meso.net  
* released only ever executable created with vvvv: the <a href="http://joreg.ath.cx/22/bildschirm-gymnastik/#more-22" class="extURL" target="_blank">bildschirmgymnastik</a> screensaver  

# vvvv 31: ~2002
* added automatic spreading through whole graphs  
* extended nodelibrary  

# vvvv 30: ~2001
* <span class="user"><a href="https://vvvv.org/users/joreg" class="extURL" target="_blank">joreg</a></span>, then intern at MESO and student at the <a href="https://www.fh-ooe.at/campus-hagenberg/studiengaenge/bachelor/medientechnik-und-design/" class="extURL" target="_blank">FH Hagenberg</a>, writes his diploma thesis "Design and Implementation of a Visual Programming Language for Videosynthesis"  
* the thesis results in a proof of concept UI for visual programming  
* MESOs existing code base is reworked into reusable nodes suitable for the dataflow UI  
* DirectX8-Rendering are added nodes  
* initial implemetation of Spreads, where many nodes had a SpreadCount input that would have to be set individually  
* initial implementation of Boygrouping  
* all efforts culminate in the first big project almost entirely run by vvvv: <a href="https://meso.design/en/projects/expo02-switzerland-cooperative-multisensory-media-space-for-national-expo" class="extURL" target="_blank">Cyberhelvetia</a>  

# vvvv 20: ~1999~2001
* <span class="user"><a href="https://vvvv.org/users/gregsn" class="extURL" target="_blank">gregsn</a></span> joins MESO as intern and starts working on the codebase  
* adds GUI to control and save parameters  
* adds triggering and morphing of sets of parameters  
* adds media libraries  

# vvvv 10: ~1997~1999
* developed as in-house coding framework at https://meso.design/ by <span class="user"><a href="https://vvvv.org/users/oschatz" class="extURL" target="_blank">oschatz</a></span> and <span class="user"><a href="https://vvvv.org/users/max" class="extURL" target="_blank">max</a></span>  
* using 3d accelerated graphic cards to create unprecedented performance on desktop PCs  
* programming in Delphi  
* no GUI  
* controlled via MIDI, e.g. Opcode MAX