---
uid: "contribution/resolume-dummy-ffgl-osc-receiver"
uid-meta: "contribution/resolume-dummy-ffgl-osc-receiver-meta"
uid-files: "contribution/resolume-dummy-ffgl-osc-receiver-files"
title: "Resolume Dummy FFGL OSC Receiver"
image: "687474703a2f2f692e696d6775722e636f6d2f655974457977432e706e67.png"
contribution: "true"
---

To use with https://github.com/Leskos/FFGLDummyParams

This is a simple wrapper for receiving the messages sent from the Dummy FFGL plugin for resolume. It provides you with just slider for using to send OSC to other aplications.

You should use the FFGLDummyParams as the first effect on your Resolume composition, otherwise when the clip/layer loses focus, it stops sending values.

Each osc sending adress in Resolume should look something like "/composition/video/effect1/param1/values "
The node provides you with a spread and with S nodes

Special thanks to Louis d'Aboville | Leskos for making this Dummy FFGL

PS: I tried using a spread instead of everything on its own. But I got messy results