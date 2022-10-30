---
uid: "contribution/nexus-ui-4v"
uid-meta: "contribution/nexus-ui-4v-meta"
comments: 
 items: 
  - uid: "212113"
  - uid: "212150"
  - uid: "212170"
  - uid: "213382"
  - uid: "214619"
  - uid: "227938"
  - uid: "229329"
  - uid: "272563"
  - uid: "272565"
uid-files: "contribution/nexus-ui-4v-files"
title: "Nexus UI 4v"
image: "Nexus_UI__0.png"
contribution: "true"
---

NexusUI is a JavaScript library of HTML5 audio interface components that can control JS apps or transmit OSC data to other applications such as VVVV,Max or anything that "eats" OSC. 
Is mobile-friendly and multi-touch compatible. It enables large-scale collaborative performances by distributing interfaces through a browser.
This is a all in one solution to create Nexus uis inside vvvv without write any single line of code, and allowing us to integrate them in our vvvv projects directly without the needing to go out of our favourite software.
It includes the Nexus ui editor, a dragging visual editor developed in vvvv ,with the help of jqueryUI, and a performer patch to use our uis and access parameters directly.
Osc is actually supported , but you must must host the interface inside a server with PHP enabled and set your port to 7475 on your software receiver. A tutorial will come.
**Its based mainly in the HTMLtexture.DX11 texture node developed by gumilastik, so you need it to run .**
[htmltexture-(dx11)](xref:contribution/htmltexture-(dx11))
Works on 32 and 64 bit and vvvv beta 34.
Here is an introduction tutorial to start, sorry about my poor english:
<div class="embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/navJhw3W4vA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
Although my skills on javascript programming were null, it was a nice exercise and learning period, open my mind to lot of possibilities based in html apps integrated with visual programming.
So expect some bugs, and not the most "clean" way of patching, but already really satisfy with the result, and it works like a charm.

NexusUI Github link : <https://github.com/lsu-emdm/nexusUI/>
API : <http://nexusosc.com/api/>

KNOWN BUGS:
in the editor , when you resize a widget and test it back actually it dont gets the new size and behaves not correctly,  not really a problem when you load it after save.

UI editor tips:
Access ID with shift key.
Delete widgets with shift+rightclick

TO DO:
-Labels: the next release will include a label option to name our widgets.
-Selectable: select any widget and change parameters from the aspect.
-Record values : save you UI state for future operations.
-Edit whats done : possibility to re-edit our saved UIs.
-All widgets working.

So i hope everybody find useful and please any feedback would be highly appreciated.
Say hello to nexus, wait for some shots of your crazy uis!
Enjoy.

