---
uid: "contribution/naudiotester"
uid-meta: "contribution/naudiotester-meta"
comments: 
 items: 
  - uid: "96673"
  - uid: "96999"
uid-files: "contribution/naudiotester-files"
title: "NAudioTester"
contribution: "true"
---

This is an example from the *Working with the vvvv-sdk* workshop at [node13](http://node13.vvvv.org).

The example was chosen to demonstrate the steps necessary to include a thirdparty managed dependency in a plugin, ie:
* use ProjectExplorer (Ctrl+j) to add a reference to the managed assembly
* add the namespace to the *using* section of the plugin

The plugin simply takes a .wav file and plays it back. This should also be a good starting point for more advanced usage of [NAudio](http://naudio.codeplex.com)s capabilities.

Note: This example requires an ASIO driver for your sound card. In case you don't have one, get it from: http://www.asio4all.com