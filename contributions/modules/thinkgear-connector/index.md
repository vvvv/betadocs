---
uid: "contribution/thinkgear-connector"
uid-meta: "contribution/thinkgear-connector-meta"
comments: 
 items: 
  - uid: "84590"
  - uid: "270982"
uid-files: "contribution/thinkgear-connector-files"
title: "Thinkgear Connector"
contribution: "true"
---

A patch for getting data from Neurosky brainwave interfaces. 

I've only tested this with the Mindwave but the documentation indicates it will work with the Mindset as well. 

Uses the thinkgear connector v2.2, should be on your install disk. 

The slow update of most values is a hardware restriction, they are only transmitted at 1hz. The raw EEG comes in at up to 512hz. It will only send a blink when it detects one. Which isn't every time you blink....

Uses many RegExpr. Could possibly just use one but had trouble with multiple pins, so just went with multiple RegExpr. 

If you are thinking about using these for a project be aware it takes a lot of filtering to get useful values. I've only just started working with it but can already tell it's going to give me 'slow' data, not fast enough to trigger drumbeats or anything like that. 

UPDATE: V2
- Fixed a null frameloop bug that would prevent TCP node working
- Added stream output and an external stream input so that you can save the raw JSON string to a text file and/or read one back. 
*Fixed a bug will null