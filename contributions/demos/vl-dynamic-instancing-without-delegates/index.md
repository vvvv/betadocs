---
uid: "contribution/vl-dynamic-instancing-without-delegates"
uid-meta: "contribution/vl-dynamic-instancing-without-delegates-meta"
comments: 
 items: 
  - uid: "270782"
  - uid: "270791"
  - uid: "270813"
uid-files: "contribution/vl-dynamic-instancing-without-delegates-files"
title: "VL Dynamic instancing without Delegates"
image: "DynamicInstancingViaName.png"
contribution: "true"
---

Hi!

I was wondering how to instance an arbitrary object based on its type name in VL for a while.

For now I offer this solution that uses the built-in Deserialize functionality, inspired by the arbitrary object spread demo in the VL Serialization help patch.

Although not perfect (any object you expect to instance has to be explicitly used in the patch (inspired by elias's LINK experience)), it's the closest solution I know of until this functionality gets native support. Is it better than Delegates with a Dictionary? You decide!

Any simplification tips appreciated.

Until next time!