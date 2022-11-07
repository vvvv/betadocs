---
uid: "contribution/android-rotationacceleration"
uid-meta: "contribution/android-rotationacceleration-meta"
uid-files: "contribution/android-rotationacceleration-files"
title: "Android Rotation&Acceleration"
image: "ara_2.png"
contribution: "true"
---

Another Xmas, another year, another small contrib for you about Android&vvvv!
A patch to get absolute orientation and linear acceleration from android devices.
**!!Orientation requires a android device with magnetic compass!!** 
This patch can use 2 different android apps, HyperIMU thru Wifi or SensoDuino thru Bluetooth.
The orientation part it's not really finished but works well if you don't need 1:1 precision(see inside the orientation node).
On some device it needs a bit of index tweaking inside the servers subpatch.
HyperIMU app is the best for performance while with from SensoDuino it's possible to get a lot more data like from the light sensor, the mic volume, the proximity sensor, gps, temperature, and more..



Happy Xmass and holidavvvvs ;)
Sapo
