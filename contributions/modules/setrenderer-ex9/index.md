---
uid: "contribution/setrenderer-(ex9)"
uid-meta: "contribution/setrenderer-(ex9)-meta"
comments: 
 items: 
  - uid: "111430"
  - uid: "111437"
  - uid: "111449"
  - uid: "111453"
  - uid: "270176"
uid-files: "contribution/setrenderer-(ex9)-files"
title: "SetRenderer (EX9)"
contribution: "true"
---

SetRenderer (EX9) is a module that combines some SetPatch-operations to manipulate/force settings of Renderer (EX9) that are not available through normal pins.

- set Componentmode of the Renderer(EX9) that normally only is available through keyboard shortcuts ( InAWindow <Alt+1>, InABox <Alt+2>, Hidden <Alt+3>, FullScreen <Alt+Enter> )
- set size and position of a windowed Renderer(EX9)
- switch off and on the border of a windowed Renderer(EX9)
- set FullScreen dimensions and refresh rates for Renderer(EX9) (only works for resolutions "allowed" by EDID/graphicscard/windows)

Although these kind of SetPatch actions generally should only be a "last option workaround", they might be useful from time to time.