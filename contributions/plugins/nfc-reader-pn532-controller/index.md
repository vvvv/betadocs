---
uid: "contribution/nfc-reader-(pn532-controller)"
uid-meta: "contribution/nfc-reader-(pn532-controller)-meta"
uid-files: "contribution/nfc-reader-(pn532-controller)-files"
title: "NFC Reader (PN532 Controller)"
contribution: "true"
---

comes as a dynamic Plugin with a slightly modified version of this [Library](https://code.msdn.microsoft.com/windowsapps/uNFC-NFC-library-d0744dab#content) (Apache License v2.0) - therefore it should work for all Readers with a PN532 Chip...
If it doesn't work out of the box, reference the uNFC.dll in your project explorer (ctr+j)

There are some hints inside the code on how to alternate the output or get other information out of it.
Right now it only outputs the NFC ID and the type, the library has a lot of other functionality, which can be easily integrated to your liking.

Tested with multiple GO2NFC121U NFC Readers (www.go2nfc.com)
Not spreadable right now, but multiple instances seem to work quite well.

developed at [StruktStudio](http://strukt.com)