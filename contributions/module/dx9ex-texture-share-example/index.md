---
uid: "contribution/dx9ex-texture-share-example"
uid-meta: "contribution/dx9ex-texture-share-example-meta"
comments: 
 items: 
  - uid: "90582"
  - uid: "90594"
  - uid: "90622"
uid-files: "contribution/dx9ex-texture-share-example-files"
title: "dx9ex Texture Share Example"
contribution: "true"
---

The zip contains an example demonstrating how to start a multiple instance project using dx9ex texture sharing, and a handy pair of send/receive texture modules.

Note: I've not extensively tested the shared memory approach for sending the texture data between instances, but it seems to work.

To use this example as intended, you must copy the vvvv folder into the project folder, replacing the dummy 'vvvv_45beta28.1' folder.  This is so the 'MAIN.bat' file, which will launch the project, can reference vvvv.exe correctly.  This also means you have a dedicated copy of vvvv per project, which for a serious project, and one that may move between different machines, is a good idea.

If you don't want to do this for whatever reason, you can launch a dx9ex enabled instance of vvvv using 'dx9ex instance.bat', which must be copied into your usual vvvv folder.

These s/r modules are in the project's subpatches folder -
SharedTexture Send (EX9.Texture).v4p
SharedTexture Receive (EX9.Texture).v4p