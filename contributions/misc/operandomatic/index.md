---
uid: "contribution/operandomatic"
uid-meta: "contribution/operandomatic-meta"
comments: 
 items: 
  - uid: "104137"
  - uid: "104139"
  - uid: "104148"
  - uid: "104155"
  - uid: "104156"
  - uid: "104163"
  - uid: "104191"
  - uid: "104192"
  - uid: "104205"
  - uid: "104207"
  - uid: "104223"
  - uid: "104708"
  - uid: "104718"
  - uid: "113885"
  - uid: "113904"
  - uid: "113921"
  - uid: "207357"
uid-files: "contribution/operandomatic-files"
title: "Operandomatic"
contribution: "true"
---

This module will save you SECONDS of time -- if not even milliseconds. Quickly create common arithmetic caluclations like **+1**, **/2**, etc. without having to always set the "Input 2" pin of the new node. Not sure, but I think puredata does it that way.

1. Just double-click into the patch as you would if you created a new node
2. type e.g. "+100" (without quotes)
3. hit enter
4. You will get a "+ (Value)" node, with its "Input 2" pin set to 100 instantly.

Place this module anywhere (e.g. in your root)

Supported Operators are: **+, -, /, *, %, =, <, >** and **@** (which will result in GetSlice (Spreads)

Will most likely break something.