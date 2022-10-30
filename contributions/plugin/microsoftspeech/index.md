---
uid: "contribution/microsoftspeech"
uid-meta: "contribution/microsoftspeech-meta"
comments: 
 items: 
  - uid: "277105"
uid-files: "contribution/microsoftspeech-files"
title: "MicrosoftSpeech"
image: "MicrosoftSpeech.png"
contribution: "true"
---

plugin for Text-to-Speech with 26 languages using Microsoft Speech Platform.


### Download Runtime
please download and install Microsoft Speech Platform Runtime (x86) and at least one Runtime Language first.
[Microsoft Speech Platform - Runtime (Version 11)](http://www.microsoft.com/en-us/download/details.aspx?id=27225)
[Microsoft Speech Platform - Runtime Languages (Version 11)](http://www.microsoft.com/en-us/download/details.aspx?id=27224)
select MSSpeech_TTS_xxx, not MSSpeech_SR_xxx!

### vs SAPI
The speech synthesis plugin has already been released in AddonPack. it's using Speech API (SAPI).
what's the difference?
* support 26 languages: [Supported Languages](http://msdn.microsoft.com/en-us/library/hh378476.aspx)
* outputs some useful progress information

### Future Deployment
* add speech recognition node
* control volume and rate realtime
* support spreading
* support Speech Synthesis Markup Language (SSML)
* export to wav

---

## Source
coming soon...