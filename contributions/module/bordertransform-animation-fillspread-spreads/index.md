---
uid: "contribution/bordertransform-(animation)-fillspread-(spreads)"
uid-meta: "contribution/bordertransform-(animation)-fillspread-(spreads)-meta"
comments: 
 items: 
  - uid: "100032"
  - uid: "100050"
  - uid: "111680"
uid-files: "contribution/bordertransform-(animation)-fillspread-(spreads)-files"
title: "BorderTransform (Animation) & FillSpread (Spreads)"
image: "bordertransform.png"
contribution: "true"
---

This package includes 2 contributions:
**BorderTransform (Animation)** generates border animations around incoming transforms with the following settings:
- how many borders shall be generated *(1 to 4)*
- the starting point *(top left, bottom left, ... )*
- border length *(0 - 1)*
- border width *(0 - 1)*

**FillSpread (Spreads)** generates and fills spreads in dependence of the incoming input. One small example:
Bin Size is 4
Input = 0.0 -> SpreadOut = 0.0/0.0/0.0/0.0
Input = 1.5 -> SpreadOut = 1.0/0.5/0.0/0.0
Input = 4.0 -> SpreadOut = 1.0/1.0/1.0/1.0

There are some more useful settings:
- shift start & end points for each slice
- set from & to values
- set initial values 


Any comments and suggestions are appreciated!