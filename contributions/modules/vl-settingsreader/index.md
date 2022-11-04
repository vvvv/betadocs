---
uid: "contribution/vl.settingsreader"
uid-meta: "contribution/vl.settingsreader-meta"
comments: 
 items: 
  - uid: "278710"
  - uid: "278712"
uid-files: "contribution/vl.settingsreader-files"
title: "VL.SettingsReader"
image: "VL.SettingsReader.png"
contribution: "true"
---

This is the first draft of a simple tool that allows you to get the values of settings inside a standard .net .config file like the ones you generate with Visual Studio.

Nothing fancy really, but hopefully it saves someone some work.

A sample config file is included as well as a simple explanation on how to use the nodes.

A standard string output version and a generic version are included.

This first draft attempts to make use of a Singleton, which means all your nodes should point at the same config file for them to behave as expected. This may change in the future.

Thanks to sebescudie and sebl for sharing their significantly more sophisticated solutions, I will try to bring in some of your ideas going forward.

Cheers.