---
uid: "contribution/linearspreadsymmetric"
uid-meta: "contribution/linearspreadsymmetric-meta"
uid-files: "contribution/linearspreadsymmetric-files"
title: "LinearSpreadSymmetric"
image: "LinearSpreadSymmetric (Spread) help_2019.05.10-05.01.24.png"
contribution: "true"
---

This version of a LinearSpread adds/removes slices from the center and phasing symmetrically to or from both it's outsides. It also handles non-integer spread counts by fading elements.
I always wanted to have this visual behaviour and was curious about a good solution for the odd/even problem. So, i started patching the logic in plain vvvv. Obviously, this needs some homework and then be translated to C# to be a single node.
As a drawback, the <span class="pin">Output</span> has an additional element when <span class="pin">Spread Count</span> is odd. Eventually the output shouldn't double the center item when interpolation is finished. 
By now, the module doesn't gracefully deal with a <span class="pin">Spread Count</span> of 0.

As always, by publishing i mainly expect to learn how this could be done easier or much more elegant by reading the comments ;}