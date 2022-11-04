---
uid: "contribution/anttweakbar"
uid-meta: "contribution/anttweakbar-meta"
comments: 
 items: 
  - uid: "76067"
  - uid: "76073"
  - uid: "76083"
  - uid: "76086"
  - uid: "76095"
  - uid: "76097"
  - uid: "76098"
  - uid: "76099"
  - uid: "76100"
  - uid: "76101"
  - uid: "76111"
  - uid: "76119"
  - uid: "76123"
  - uid: "76124"
  - uid: "76140"
  - uid: "76146"
  - uid: "76147"
  - uid: "76153"
  - uid: "76154"
  - uid: "76155"
  - uid: "76161"
  - uid: "76178"
  - uid: "76198"
  - uid: "76260"
  - uid: "76265"
  - uid: "76290"
  - uid: "76307"
  - uid: "76313"
  - uid: "76454"
  - uid: "76464"
  - uid: "76533"
  - uid: "83637"
  - uid: "83682"
  - uid: "83705"
  - uid: "92085"
  - uid: "92150"
  - uid: "92243"
  - uid: "92260"
  - uid: "93604"
  - uid: "93799"
  - uid: "112730"
  - uid: "112815"
  - uid: "112817"
  - uid: "112834"
  - uid: "153677"
  - uid: "153728"
  - uid: "153768"
  - uid: "153837"
  - uid: "156588"
  - uid: "239640"
  - uid: "239719"
  - uid: "239746"
uid-files: "contribution/anttweakbar-files"
title: "AntTweakBar"
image: "AntTweakBar.png"
contribution: "true"
---

It's finally here! New GUI plugin for vvvv is introduced.

[AntTweakBar](http://anttweakbar.sourceforge.net/doc/) is a simple and easy-to-use GUI library for 3D graphic applications.
You can add/remove variables and create group few steps.

NOTE:
This plugin is under development. any requests and bug reports welcome. 

### Hints
* no more limitation of the number of variables
* variables saves until delete TweakBar node
* can use only for one renderer

### Known Issues
* keyboard input with long press is not support yet

### Future Deployment
* support more parameters for tweakbar and variables

---

### Change Log
**2012.2.14 (v0.91)**
* support full-screen mode
* fixed renderer re-size bug
* no more output NIL if disconnect and connect layer out again

**2012.12.25 (v0.92)**
* fixed fixed error when using with >beta28

**2014.6.9 (v1.0)**
* re-write plugin with 100% C#
* support save & load tweakbar
* new variable Types
** **Button**: like a Bang
** **Enumerations**: like an Enum
* new nodes
** **Event**: control Mouse, Keyboard, Window Size change (remove these pins from TweakBar node)
** **GetEnum**: get Enum index and string from TweakBar
** **Writer**: save tweakbar status & variables as text file
** **SetVariable**: set variables & update GUI from patch
* support across multi-monitor when /dx9
* no more limitation of number of variables
* TweakBar node outputs Transform Out. it is useful for custom background with Quad
* improve keyboard input
---

## Source
source code available on github. (ver1.0 will coming soon!)
https://github.com/mino218/vvvvPlugins