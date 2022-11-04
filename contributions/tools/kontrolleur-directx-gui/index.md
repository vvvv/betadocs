---
uid: "contribution/kontrolleur-directx-gui"
uid-meta: "contribution/kontrolleur-directx-gui-meta"
comments: 
 items: 
  - uid: "157093"
  - uid: "159970"
  - uid: "174647"
  - uid: "174648"
uid-files: "contribution/kontrolleur-directx-gui-files"
title: "Kontrolleur DirectX Gui"
image: "_KontrolGui-DX9 GUI.png"
contribution: "true"
---

continuing from this thread [getting-and-setting-kontrolleur-values-in-a-patch](https://discourse.vvvv.org/t/getting-and-setting-kontrolleur-values-in-a-patch)

You can Control+K to expose an iobox to the GUI, you can edit the iobox itself in the patch, or use the gui to do so. Double clicking on numbers or text in the right hand columns will allow keyboard entry, sliders where the names are will also set values.
Presets can be global if you use the AllControls button, or per patch if you select a patch to edit. Right click to record, left to play them.
Use the forums or contributions page for bugs and suggestions

You wait years for an easy GUI for vvvv and then 2 come along at once [anttweakbar](xref:contribution/anttweakbar)
Maybe anttweakbar can be setup to use kontrolleur too (and your new timeliner joreg, hehe ;)

Included are both DX9 and DX11 (for beta32) versions in 1 patch, delete the renderers you don't need!

Catweasel

To do's
network into the patch from other pc's for remote access/multiple users.
Enums, I was hoping to use ints to select the enum and write the name into a text iobox, but the gui doesnt pickup on that, so not sure how to do this in a readable way...

Bugs, if you delete or add controls when you've already made presets, you presets will get a bit wacky, as they're address via a list not by names.
TODOmap spits an exception on loading
Add more below...