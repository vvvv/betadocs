---
uid: "contribution/watchdog"
uid-meta: "contribution/watchdog-meta"
uid-files: "contribution/watchdog-files"
title: "WatchDog"
contribution: "true"
---

Uses Shellexecute to launch a process and the watches for a heart beat by udp, if it doesn't recieve one, after a polite wait it will kill the task and restart it.

( Dev's does this look sound, are the shell execute's 'is running' and 'kill' robust enough? )