---
uid: "contribution/pd-patch-loader"
uid-meta: "contribution/pd-patch-loader-meta"
comments: 
 items: 
  - uid: "96672"
  - uid: "96958"
  - uid: "96959"
uid-files: "contribution/pd-patch-loader-files"
title: "PD Patch Loader"
contribution: "true"
---

This is an example from the *Working with the vvvv-sdk* workshop at [node13](http://node13.vvvv.org).

The example was chosen to demonstrate the steps necessary to include a thirdparty native dependency in a plugin, ie:
* use ProjectExplorer (Ctrl+j) to add a reference to the managed wrapper of the native dependency
* add the namespace to the *using* section of the plugin
* copy the native dependency to the output directory (\bin) manually

The plugin simply takes a .wav file and a .pd file. While the file is played back using the [NAudio](http://naudio.codeplex.com) the processing is routed through the given pd-patch via the [libpd](http://libpd.cc/) library which can even be sent values to from the vvvv-patch.

Note: This example requires an ASIO driver for your sound card. In case you don't have one, get it from: http://www.asio4all.com