---
uid: "contribution/feedbackcs-(dx11.texture2d)"
uid-meta: "contribution/feedbackcs-(dx11.texture2d)-meta"
comments: 
 items: 
  - uid: "108502"
  - uid: "218717"
  - uid: "219628"
uid-files: "contribution/feedbackcs-(dx11.texture2d)-files"
title: "FeedbackCS (DX11.Texture2d)"
image: "FeedbackCS help-Renderer.png"
contribution: "true"
---

This module helps to get texture feedback in DX11.
While FrameDelay(DX11.Texture2d) is a bit glitchy, this one made with Compute Shader is more stable for now.

You can add some changes to previous frame texture just in code of CS.

I would like to add features that we had to use with real framedelay like texture transform or filtering but have no any good results with these yet.
Any notes welcome.