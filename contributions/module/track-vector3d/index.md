---
uid: "contribution/track-(vector3d)"
uid-meta: "contribution/track-(vector3d)-meta"
comments: 
 items: 
  - uid: "157464"
  - uid: "157465"
  - uid: "157690"
  - uid: "158314"
  - uid: "158818"
  - uid: "185486"
  - uid: "196397"
  - uid: "196461"
uid-files: "contribution/track-(vector3d)-files"
title: "Track (Vector3D)"
image: "Track (Vector3D) help-DirectX Renderer_2014.06.22-02.13.19.png"
contribution: "true"
---

This contribution helps to restore a certain spread order from a unordered list of coordinates. This is necessary if you do touch detection or even 3D blob tracking yourself or if you use a Tracker, that handles IDs badly.

Instead of doing it in a plugin, I tried to do as much as possible with good oldschool patching. It would not have worked without the advanced spread nodes, so thanks to woei.

The upload includes generic plugin NearestPair, which can be used similarily to ConnectAll or NearestNeigbour.

Edit:
This contribution is part of the [PointCloud toolkit](xref:contribution/kinecttoolkitdx11) and its most current version can be found at [github](https://github.com/letmp/KinectToolkitDX11/tree/master/nodes/modules/ThirdParty/Track%20(Vector3D)).