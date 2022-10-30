---
uid: "contribution/deselect"
uid-meta: "contribution/deselect-meta"
comments: 
 items: 
  - uid: "61728"
uid-files: "contribution/deselect-files"
title: "Deselect"
contribution: "true"
---

Performs an inverse select operation, by grouping subsequent identical slices of a spread into bins.
If you feed the output of the deselect node back into the select node, you receive your original spread.
Useful if you need to 'compress' your spread and don't know the original bin sizes.