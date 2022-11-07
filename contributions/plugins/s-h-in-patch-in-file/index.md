---
uid: "contribution/s h-(in-patch-in-file)"
uid-meta: "contribution/s h-(in-patch-in-file)-meta"
comments: 
 items: 
  - uid: "49902"
  - uid: "55259"
  - uid: "55341"
  - uid: "55401"
  - uid: "70520"
  - uid: "70521"
uid-files: "contribution/s h-(in-patch-in-file)-files"
title: "S+H (in patch, in file)"
contribution: "true"
---

two nodes in this plugin:

S+H (in patch) - saves the data into a config pin
this is easiest to use and is nice and tidy
you obviously cant use this one if you've got multiple instances of the same patch (they'll overwrite each other!)

S+H (in file) - for this one you have to define a filename on the filename pin
it saves the data in an external file so you dont have issues with multiple instances of the same patch
and you can also have two different patches working with the same file (e.g. a calibration patch, and a runtime patch)
data is stored in something like CSV
the path of the filename is relative to the path of the patch holding the node.


further advancements (not implemented)
auto save/load on close/open patch