---
uid: "contribution/working-texture-queue-fix-for-beta26"
uid-meta: "contribution/working-texture-queue-fix-for-beta26-meta"
uid-files: "contribution/working-texture-queue-fix-for-beta26-files"
title: "Working texture Queue fix for beta26"
contribution: "true"
---

OK, using a value queue to manage the slice indices and a second Buffer makes this now work like a real Queue.  At least it works for my use of Queue, which is as a delay for texture feedback.

New module attached.

I left the first Buffer and Buffer Indices outputs just for flexibility.
