---
uid: "contribution/operatorszip-(value)"
uid-meta: "contribution/operatorszip-(value)-meta"
uid-files: "contribution/operatorszip-(value)-files"
title: "OperatorsZip (Value)"
contribution: "true"
---

You may have found yourself in need to add\sub\mul\divide the same spread of values to many different other spreads, and you may got bothered of generating nodes and links and so on.
OperatorsZip bundle has four nodes that may help you:

* AddZip
* SubtractZip
* MultiplyZip
* DivideZip

The first pin of each of these nodes will be added to \ be subtracted from \ be multiplied by \ divide the other spreads fed into Dynamic Input Count pins.
So, if you have to multiply a number of spreads by (0.333,0.5), the spreads in Output will return the result of this operation and will have the same SliceCount as their respective Input.
This could theoretically ease the use of SetPatch and such.
---
There also a .sln file; just in case.
---
To be released: a VL version (as soon as I get a minimum grasp on it)