---
uid: "contribution/texture-sharing-from-gamma-to-beta-and-back"
uid-meta: "contribution/texture-sharing-from-gamma-to-beta-and-back-meta"
comments: 
 items: 
  - uid: "277109"
  - uid: "277110"
uid-files: "contribution/texture-sharing-from-gamma-to-beta-and-back-files"
title: "Texture sharing from gamma to beta and back"
contribution: "true"
---

Modules / helpers for texture sharing between beta/DX11 and gamma/stride.
Also contains helpers to match stride and beta cameras.

Currently uses UDP for sharing the handles and camera matrix.
Something like [VL.SharedMemory](https://github.com/cnisidis/VL.SharedMemory) might be better but I didn't want to add external dependencies.