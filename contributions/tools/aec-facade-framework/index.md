---
uid: "contribution/aec-facade-framework"
uid-meta: "contribution/aec-facade-framework-meta"
uid-files: "contribution/aec-facade-framework-files"
title: "AEC Facade Framework"
contribution: "true"
---

A patch framework for running different visualisation-patches on the Ars Electronica Center's media facade. Available patches can be selected and a 2D (unfolded) and 3D preview are shown while the individual lights colors are sent to the AECs facade controller software via UDP.
The framework also includes a simple template patch to start from when creating a new visualisation for the facade.
<!--break-->
Initially created for the *Algorithmic Arts* course in the [Digital Media master class at the FHS-Hagenberg](http://www.fh-ooe.at/campus-hagenberg/studiengaenge/master-studien/digitale-medien/), results of which [can be seen here](http://dm08.wordpress.com/). Also note the [processing AEC_FacadeFramework](http://dm08.wordpress.com/aec-plugin/) that was developed by students of the same course.

## Requirements
* vvvv >= 40beta22
* addonpack_01

## Sources
latest sources of the framework are available via sourceforge from:
^ https://vvvv.svn.sourceforge.net/svnroot/vvvv/tools/AEC_FacadeFramework/trunk^

1. Usage
* Start _AEC_Facade.v4p
* enter target hosts IP (the one running the AEC Facade Simulator and Controller Software)
* enter target port
* toggle sending color values via UDP on|off
* using a right-mousebutton-click! select one of the available visuals from the list to the left. 

* use rescan to update the list when you added patches to \contents while the AEC_Facade_Framework was running
* "show light tiles" optionally show the unfolded facade sides as overlay grid
* "show lights" optionally constrains the rendering to the facades actual pixel resolution
* "show content outside of facade" optionally hides the rendering outside the regions of the facade.


## Creating a new visualisation
It is best to start a new visualisation from the provide template patch by simply making a copying the _Template directory and renaming it. Then also rename the _Template.v4p patch inside that directory (the filename is the one showing up in the selectable list).

As you can see in the template patch, the main thing you have to provide now is some *layers* that render to the *Flat Preview* renderer. You can specify whether the renderers backbuffer is to be cleared or not (if not, you can achieve an afterimage-like effect by drawing a quad with alpha~0.1 covering your whole scene) and you can give yourself some credits for the patch. 

## Replacing the DefaultMapping
Advanced users may be interested in changing the basic layout of the unfolded facade sides. Then it is best to make a copy of the DefaultMapping.v4p subpatch local to your content directory and modify its content (which should speak for itself to such advanced users). 

1. Change Log
## v1 04 06 09
* initial release