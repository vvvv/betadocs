---
uid: "contribution/ffmpeg4vvvv"
uid-meta: "contribution/ffmpeg4vvvv-meta"
uid-files: "contribution/ffmpeg4vvvv-files"
title: "FFMpeg4vvvv"
image: "logo-ffmpeg.png"
contribution: "true"
---

####  ffmpegInfo
**ffmpegInfo**is running *ffprobe.exe* in the background to extract video file information, then parses the result once, when the program has completed its execution.



####  ffmpegConvert
**ffmpegConvert**first run **ffmpegInfo**to extract videofile information, then, when it is completed, builds command line arguments, at the second stage the patch is starting ffmpeg.exe in background mode and parses in real-time the output (stdErr) to report the current progress, at the end plays the converted video file, hopefully ;)

<div class="box">
Note:
###  You need:
Exec plugin [/contribution/exec](/contribution/exec)  

FFMPEG windows (static) binary from <http://ffmpeg.zeranoe.com/builds/>

*All in all this is an example for Exec node, how external programs can be used, it is not native c# binding to ffmpeg.*

</div>




have fun 

more information about **ffmpeg**(http://ffmpeg.org/legal.html)