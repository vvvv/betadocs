---
uid: "contribution/binary-operators"
uid-meta: "contribution/binary-operators-meta"
comments: 
 items: 
  - uid: "71548"
uid-files: "contribution/binary-operators-files"
title: "Binary Operators"
contribution: "true"
---

If you know how to use << >> & | ~ ^ on values, this is for you. If you do not know: these operate on the binary values of the data directly and therefor speed up things sometimes with the cost of being more complicated to code - e.g. division by 2 on an integer (not a float or double) maps to

```
value >> 1
```

I missed them sparsely, so i made a quick and rough implementation.

You can also get LeastSignificantBytes (LSB) and MostSignificantBytes (MSB) from numerical values, for e.g. building MIDI messages i a patch more easly.
It also includes a re-implemetaion of "Bit", named "Fastbit" using shifting and being spreadable.


Nodenames: BitAND, BitOR, BitXOR, BitNOT, FastBit, LSB, MSB, LSB+MSB

Any bugs, issues and feature requests should be posted at https://github.com/jens-a-e/V4BitwiseOperators/issues or here.

Get it the source here https://github.com/jens-a-e/V4BitwiseOperators



P.S.: I know, providing a help patch is next on the list.