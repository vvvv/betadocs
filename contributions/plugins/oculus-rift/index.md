---
uid: "contribution/oculus-rift"
uid-meta: "contribution/oculus-rift-meta"
comments: 
 items: 
  - uid: "101568"
  - uid: "103344"
  - uid: "103346"
  - uid: "103350"
  - uid: "103372"
  - uid: "103389"
  - uid: "103390"
  - uid: "103391"
  - uid: "103396"
  - uid: "103430"
  - uid: "103549"
  - uid: "103601"
  - uid: "103605"
  - uid: "156749"
  - uid: "161711"
  - uid: "161830"
  - uid: "161836"
  - uid: "163456"
  - uid: "164031"
  - uid: "164097"
  - uid: "164129"
  - uid: "164530"
  - uid: "164541"
  - uid: "164559"
  - uid: "164586"
  - uid: "164819"
  - uid: "164844"
  - uid: "164847"
  - uid: "164849"
  - uid: "164852"
  - uid: "165414"
  - uid: "181810"
  - uid: "188442"
  - uid: "189968"
  - uid: "191202"
  - uid: "192227"
  - uid: "204194"
  - uid: "225074"
uid-files: "contribution/oculus-rift-files"
title: "Oculus Rift"
contribution: "true"
---

<div class="box">
Note:
These nodes might be outdated, use [VVVV.OpenVR](xref:contribution/vvvv.openvr) for VR related projects. 
</div>

Here is an initial take on the Oculus SDK (sensor access + distortion shader). It's mostly ported from the Unity3D stuff.

Note that there seems to be buggy behaviour in vvvv in regard to the HID device (Tracker DK) that the Oculus installs. If vvvv is running (has nothing to do with this patch, just open vvvv), no other application can access the Oculus. And, more importantly, vvvv will prevent itself from using it if just started.

The current workaround seems to be:
* another application (e.g. PreventDeviceEnumeration.exe) has to open a connection to the Oculus,
* start vvvv and open the oculus patch,
* disable the OculusRift node,
* close the other application,
* enable the OculusRift node in the patch.
Could of course be done with a .bat file or something.

A simple .exe (PreventDeviceEnumeration.exe) which just opens a connection to the device and streams the values is provided within this package, so you can block vvvv from doing it's dark, sinister and unfortunate magic.