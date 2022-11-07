---
uid: "contribution/vl.io.xbox360controller"
uid-meta: "contribution/vl.io.xbox360controller-meta"
uid-files: "contribution/vl.io.xbox360controller-files"
title: "VL.IO.Xbox360Controller"
image: "VL.IO_.Xbox360Controller.png"
contribution: "true"
---

This package adds nodes allowing you to use an Xbox 360 Controller in VL easily.

Similar pin layout as this plugin for vvvv [xbox360controller](xref:contribution/xbox360controller) but adds a Is Connected output and also there are 3 versions of the node available:
1. Standard - Outputs all controller inputs as either floats or booleans
2. Vector - Standard with thumbsticks as Vector2 values
3. State - Outputs a single Record object

1. Install using nuget in the commandline:
```
nuget install VL.IO.Xbox360Controller
```
2. Add dependency to VL.IO.Xbox360Controller via the node browser
3. Find nodes in IO.Xbox360Controller

A demo patch is included in examples folder in the nuget install location

Enjoy