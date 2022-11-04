---
uid: "contribution/operandomaticplusiomagic"
uid-meta: "contribution/operandomaticplusiomagic-meta"
comments: 
 items: 
  - uid: "107657"
  - uid: "207356"
uid-files: "contribution/operandomaticplusiomagic-files"
title: "OperandomaticPlusIOMagic"
contribution: "true"
---

Extension to sagishi's Operandomatic: [operandomatic](xref:contribution/operandomatic)

All of the original Operandomatic functionality left untouched (I hope) plus added feature to allow creating of nxn IOBoxes by doubleclicking and typing CategoryRowsxCols where Category is one of the following characters: i,v,d,b,c,t,s representing Integer, Value, Double (same as Value), Bang, Color, Toggle, String and the xCols can be left out to create a one dimensional iobox instead of two dimensional.

examples(doubleclick and type):

To create 3x3 Value IOBox:   	v3x3     (or    d3x3)
To create 5x2 Integer IOBox:	i5x2
To create 8x1 Bang IOBox:	b8
To create 2x2 Toggle IOBox:	t2x2
To create 9x9 Color IOBox:	c9x9
To create 1x4 StringIOBox:	s1x4

Not case sensitive and ignores at least some whitespace.

Plus optionally add a prefix to avoid collisions with node list, tweak cell size and if grid should be shown.

Quickly made so will probably think of more options to add later... 