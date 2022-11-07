---
uid: "contribution/patterntouch"
uid-meta: "contribution/patterntouch-meta"
comments: 
 items: 
  - uid: "96402"
  - uid: "96525"
  - uid: "96534"
  - uid: "96701"
  - uid: "98058"
  - uid: "98059"
  - uid: "98063"
  - uid: "98068"
  - uid: "98309"
  - uid: "98457"
  - uid: "98701"
uid-files: "contribution/patterntouch-files"
title: "PatternTouch"
image: "robot.png"
contribution: "true"
---

### PatternTouch - multi touch framework for vvvv, based on common user interaction patterns.
#### Features:
* Translate, Scale, Rotate gestures (all via center).
* Alpha channel support.
* GPU based intersection analysis, especially useful for complex meshes. 
* Display List support via Group node.
* Created with vvvv in mind.

#### In next releases:
* Pan and Zoom gestures.
* Transformation limits with iOS like behavior.
* Multidirectional swipe gesture.
* Photo Gallery module.

#### Limitations:
* No sorting support. All transformations always sorted by ID.
* No complex transformation hierarchies. For example, if you have a touchable element in container and want to scale this container, you need to touch container only in empty places. Upper object always receive all blobs.

#### Bugs:
* VPA (PatternTouch Split) outputs zero AspectRation matrix if no input connected.

Sources - https://github.com/smakhtin/PatternTouch