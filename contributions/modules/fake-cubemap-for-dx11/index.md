---
uid: "contribution/fake-cubemap-for-dx11"
uid-meta: "contribution/fake-cubemap-for-dx11-meta"
uid-files: "contribution/fake-cubemap-for-dx11-files"
title: "Fake Cubemap for DX11"
image: "cubemap2.jpg"
contribution: "true"
---

I needed a proper and artifact-less way of creating spherical landscapes and i thought the best way to realize it is using cubemaps. unfortunately current DX11 implementation misses rendering to proper cube textures so i utilized volume textures for the same task.
It's pure hackery but seems to be working.