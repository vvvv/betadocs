---
uid: "contribution/connectall"
uid-meta: "contribution/connectall-meta"
comments: 
 items: 
  - uid: "99913"
  - uid: "99916"
  - uid: "99921"
  - uid: "102470"
  - uid: "102625"
uid-files: "contribution/connectall-files"
title: "ConnectAll"
image: "ConnectAll (3d) help-DirectX Renderer_2010.12.09-23.33.35.png"
contribution: "true"
---

This is an example from the *Plugin Coding for Beginners* workshop at [node10](http://node10.vvvv.org). 

It takes a spread of 3d vectors and for each of those checks the distance to all other vectors. If that distance is below a given threshold the two vectors involved are added to the output spread. The actual distance between the two is returned on a second output pin. 

for beta24.1: put the directory from the .zip in your \plugins directory
for beta>24.1: does not need to be in the \plugins directory, desktop will do