---
uid: "contribution/notuiv"
uid-meta: "contribution/notuiv-meta"
comments: 
 items: 
  - uid: "251748"
  - uid: "251805"
  - uid: "251999"
  - uid: "252006"
  - uid: "253112"
  - uid: "268649"
  - uid: "268728"
  - uid: "268738"
  - uid: "268830"
  - uid: "268836"
  - uid: "268842"
  - uid: "268846"
  - uid: "268854"
  - uid: "268861"
  - uid: "270553"
  - uid: "270554"
  - uid: "270740"
  - uid: "270743"
  - uid: "270745"
  - uid: "270751"
  - uid: "272535"
  - uid: "272539"
  - uid: "272564"
title: "Notuiv"
image: "headerquad.png"
contribution: "true"
---

<div class="vimeo embed-responsive embed-responsive-16by9 mt-3 mb-4">
    <iframe title="vimeo-player" data-src="https://player.vimeo.com/video/268043752/d05f02a82a" width="640" height="360" frameborder="0" allowfullscreen></iframe>
</div>
1.  ₪iv

Notui is a UI behavior package written entirely in C# providing a robust skeleton for your UI elements. The intention here was to keep VVVV's vast drawing capabilities while eliminating the cobweb of doom usually present while patching UI logic. The result is a mostly dataflow friendly system which separates structure, stateful-logic and rendering. Note also that Notui is a C# library first and Notuiv is its VVVV implementation. This again means all the features of Notui theoretically can be accessed in VL and simply fetched from Nuget.org. This also means that you can patch your own element types and behavior delegates in VL. This is untested yet though.

##  tl;dr, <a href="vpms://raw.githubusercontent.com/vvvvpm/vpdb/master/MESO/Notuiv/github.latest.vpack">get it with vpm</a>

[But get vpm first](https://github.com/vvvvpm/vpm/releases/latest)
if you hate vpm though you have github releases: https://github.com/meso-unimpressed/Notuiv/releases :P

And also it doesn't depend on either mp.essentials nor mp.dx. Yay I guess :P
But it requires vvvv beta36+ and vux's DX11 1.1+ but 1.2+ is recommended from github. It doesn't work with beta35.8 or older because how AllowFeedback is changed to a much smarter interface in beta36. But you don't have to think about these if you use vpm ;)
.NET 4.7 is required. Make sure your Windows 7+ is updated properly or install it from https://www.microsoft.com/en-US/download/details.aspx?id=56116

Notui is available through Nuget for Visual Studio (Code) and VL.
```
PM> Install-Package Notui
```

##  Example:

![title](https://vvvv.org/sites/default/files/imagecache/large/images/https://media.giphy.com/media/AicKsuWDSdUapo8cl0/giphy.gif)

The above thing is a girlpower patch demoing a simple application structure with Notuiv inside. This is the patch behind it:

![title](https://vvvv.org/sites/default/files/imagecache/large/images/https://i.imgur.com/kET0vAp.png)

And expanded:

![title](https://vvvv.org/sites/default/files/imagecache/large/images/https://i.imgur.com/F1dUOyF.png) 

As you can see it's relatively simple to set up this 2 draggable windows with stateful content and animated declarative transitions patched 100% in VVVV with Notuiv.

##  Features

* **Separate semantics describing UI structure and its stateful realization**
** Element Prototypes and their Instances
* **Elements are nestable**
** which means you can organize them into parents/children hierarchy and children will inherit their parent's space
* **Hit-testing touches and other pointers are happening in full 3D**
** with arbitrary View and Projection matrices, but it won't make your life harder in 2D
* **Separate events for hovering, interacting and the beginning/ending of both.**
** You also have full control over how elements are receiving touches, or blocking touches from elements beneath them.
* **Special events for mouse interactions**
** Notui also provides you with a Mouse wrapper (same as we're all used to in vvvv)
* **Touch Intersections provide you with both world space and element space coordinates**
** Intersections also have their own space which are also provided with Transforms. So you can easily create 3D content on the place of the interaction. With this you can also get the tangential space of the surface of 3D elements at the point of interaction.
* **Interaction Behavior delegate classes written for CLR (C# or VL) attached to elements**
** which are executed on them each frame. Currently Notui comes with few but it has an easy API to implement your own, and I also have plans for waay more:
** advanced (picture) stack sliding with inertia in 3D
** value sliders
** mouse wheel scrolling with inertia
** moving to the top on touch (only makes sense in 2D)
** and more to come...
* **Several shapes for hit-testing**
** Currently available:
** infinite plane and rectangle
** circle and segment
** planar arbitrary polygon,
** box and sphere
** and more to come...
* **Effortless Fading in and Fading out effects even with Staggering and Declarative transform transitions**
** You just feed the present list of your element prototypes into a Notui Context and it'll take care of keeping element instances for fading out which are no longer present among your prototypes. If set then Notui can also automatically apply a Damper transition for the transforms changed from the Prototype.
* **Notui considers touch force**
** It uses that to determine if a touch is hovering over an element or actually touching it. This way mouse interaction and touches from windows are dealt with the same semantics, but you can also supply your own touches from any other device which might actually support real force or pointer-screen distance. (like Intous tablets) Also you can do anything else with it yourself ;)
* **Both Prototype elements and element Instances can hold any number of arbitrary attached objects and values**
** which can be modified on Instances to keep the side-effects of your behaviors OR interact with external data represented by a Notui element. You can also attach DX11 resources.
* **Multiple and nestable Notui Contexts**
** which are the core of this package, managing everything including hit-testing, instantiating and organizing instances. You can have as many of them as you like, you can even attach one to any element and make it act like either "overflow: hidden" in CSS or for multiple viewports. Contextception.
* **Elements are dealt with asynchronously and in parallel**
** Running at least 2 times faster on modern Intel i7 CPU's than it would synchronously. Interaction Behavior delegates are also run in this parallel threads.
* **In VVVV prototypes are created in a similar fashion as layers in DX11**
** And fed to Context nodes which are just like Renderer nodes in DX11
* **Opaq (Object Path Query) implementation on nested elements**
** In a nutshell it allows nested object query on anything with couple of delegate functions (like XPath for XML) coming with md.stdl. You can also have Regex instead of regular absolute path steps. See help patch of Sift (Notui.Context Opaq) for more info.
* **Notui has XML docs for all of its classes and public API's**
* **Notuiv in VVVV has helpful girlpower and help patches for every node***

*where it makes sense.

##  Roadmap:

* **next minor version**
** Hittesting arbitrary DX11 geometry
** (De)Serialization of element instances via XML or MessagePack
** More basic interaction behaviors like Toggle buttons, radio buttons
** Maybe VL girlpower. Maybe.
* **plans**
** Camera movement with multitouch
** Context Behaviors
** Raymarching distance fields (maybe)

![title](https://vvvv.org/sites/default/files/imagecache/large/images/https://media.giphy.com/media/C9x8btCog0XwnrZ05g/giphy.gif) 

##  Repos:

https://github.com/meso-unimpressed/Notui
https://github.com/meso-unimpressed/Notuiv

The name comes from the fact that this library only handles structural definitions, behavioral patterns, and state-ful element management, but it's not providing ways of drawing those elements. This decision made it possible to use it in a graphics backend agnostic way and maintain complete user experience and artistic freedom.

**Side note:** Now for those who want to use Notui outside of VVVV don't get fooled or intimidated by the lines of code count of Notuiv implementation, that amount of boilerplate code is not a Notui specific phenomena . It's an inherent structural issue with how VVVV works. It's a general rule of thumb that if you want to implement a large library solving a big set of problems in a very modular way with lot's of information on their building blocks, VVVV's plugin interfaces requires thousands if not ten-thousands of lines boilerplate to deal with all the conditions a plugin can have. *This is 100% solved in VL though.*

**Disclaimer on the logo:** Notui have nothing to do with Israel's new shequel. That symbol just looks great and resembles an 'n' and a 'u' interlocked, throw in an 'i' and you'll get Notui \o/. But if anybody feels offended by this for any serious reason (like if an Israeli person really feel like their national currency symbol is being abused by random UI libraries for simply aesthetic reasons which has nothing to do with it, or with Israel) I'll immediately change it.

###  Made in [MESO](https://meso.design)

![title](https://vvvv.org/sites/default/files/imagecache/large/images/https://media.giphy.com/media/1eExH5lNIClZPq9fY8/giphy.gif) 