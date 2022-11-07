---
uid: "contribution/obsolete-see-addonpack-openniskeleton-plugin-with-depth-output"
uid-meta: "contribution/obsolete-see-addonpack-openniskeleton-plugin-with-depth-output-meta"
comments: 
 items: 
  - uid: "69922"
  - uid: "69939"
  - uid: "70144"
  - uid: "70879"
  - uid: "70881"
  - uid: "70882"
  - uid: "70898"
  - uid: "70992"
  - uid: "70994"
  - uid: "70997"
  - uid: "70999"
  - uid: "71005"
  - uid: "71013"
  - uid: "71018"
  - uid: "71020"
  - uid: "71024"
  - uid: "71025"
  - uid: "71028"
  - uid: "71029"
  - uid: "71155"
  - uid: "72413"
  - uid: "72535"
  - uid: "73533"
uid-files: "contribution/obsolete-see-addonpack-openniskeleton-plugin-with-depth-output-files"
title: "[OBSOLETE, see Addonpack] OpenNISkeleton Plugin with depth output"
image: "Capture-2.jpg"
contribution: "true"
---

Here's a quick and dirty hack as a proof of concept.  The depth map returned by OpenNI is actually a bitmap where each 16-bit pixel contains 13 bits of depth information as the distance in millimeters (roughly).

Since textures consist of 8-bit values for RGBA, I split the depth data up into the B and G values; the uppermost 8 bits into the Blue (MSBs), and the remaining lower 5 bits into the Green (LSBs).

By using Pipet, these values can be recombined to get the original depth value.  Also, this data can be processed in an effect shader for doing distance slicing, etc.

This probably should be rolled into the Kinect OpenNI Library package, but this got me going quickly to test out some ideas without having to install the 12 and a half buckets of stuff needed to build plugins.  The change is actually very minor.

In the v1 help patch you can click on points in the depth image to read the distance.

The v2 help patch shows the use of an effect to translate the depth data into a non-AGC greyscale, and conversion of the Kinect depth data into a world-coordinate point cloud.

Cheers!
