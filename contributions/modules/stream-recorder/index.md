---
uid: "contribution/stream-recorder"
uid-meta: "contribution/stream-recorder-meta"
uid-files: "contribution/stream-recorder-files"
title: "Stream Recorder"
contribution: "true"
---

Records any data to file with timestamps. Plays it back much like a filestream node.

Originally developed to record infrared tracking data from the contour node and play it back later.

The files it makes are sort-of human readable, for small data sets.

It's not sexy and it's not perfect but it gets the job done. Use at your own risk.

Issues
- No passthrough when play is off, intentional behavior
- Reverse speed not reliable
- Files append. Recording a short file over an existing long file can cause weird behaviour
- Opening large files can take a very long time
- No record safe function, very easy to record over existing files
- If you are playing when first recording you may have to rehit play
- Probably has issues with maximum input length but I haven't run into them yet.
- Bug where quotation marks in the string input screw things up. 