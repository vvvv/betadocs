---
uid: "contribution/polymap-(beta-vl-only)"
uid-meta: "contribution/polymap-(beta-vl-only)-meta"
uid-files: "contribution/polymap-(beta-vl-only)-files"
title: "PolyMap (beta, VL only)"
image: "Untitled-3Artboard 1.jpg"
contribution: "true"
---

In order to get my head around a (triangulization) plugin I intend to write I decided to start by patching the logics surrounding it and it turns out- thanks to the glorious power of vvvv and the (new?) ClippingEar plugin- a simple version of this can be fully patched; and here it is:

Draw any polygonal shape on a texture to select this part of the texture, then transform this (textured) shape in your output/projection. Multiple shapes supported.
This can also be used in 3d mapping situations, eg in Egypt, as a last step to compensate for differences in virtual/real properties of your mapping object/projectors.

NOTE:
-based on PointEditor -> VL ONLY; basically you can exchange the PointEditor with a spread to get this to work without VL, not done here for ease of use.
-still beta for several reasons, mostly because I've just done this now and haven't tested it ;) also triangulization won't be fine enough for heavy output transformations (will "break" your texture), probably not fast enough too; but it should work fine in simple cases, especially when working with triangles.

ToDo:
-better triangulization (where needed); *will work on this asap.*
-transform options for individual shapes; *might come if PointEditor supports multiple lines*
-bezier shapes; *requires to add support for closed bezier curves to BezierEditor*
-option to add holes to shapes, *might come with better triangulization*
-DX11