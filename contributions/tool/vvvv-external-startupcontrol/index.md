---
uid: "contribution/vvvv.external.startupcontrol"
uid-meta: "contribution/vvvv.external.startupcontrol-meta"
comments: 
 items: 
  - uid: "75999"
  - uid: "92117"
uid-files: "contribution/vvvv.external.startupcontrol-files"
title: "VVVV.External.StartupControl"
image: "Screenshot.png"
contribution: "true"
---

Choose a patch or executable, and a target CPU percentage.

Then whenever the CPU usage % is below a threshold, the progress bar will increase (and decrease if it's above the threshold).

When the CPU usage has been low for 10 seconds, the app will load the patch you've selected and close itself.

Also* pressing the escape key cancels the process, so you can stop the patch loading on startup.
* (and the reason I made it in the first place)

Saves all its settings in an external file.

1.  Usage
1. Run the application
1. Select a patch using the 'Select' button (this will popup by default the first time)
1. Select a target CPU usage threshold with the 'Target' slider
1. Hit Cancel
1. Put a shortcut to the application in your startup folder.
1. Reboot and enjoy!