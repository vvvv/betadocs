---
uid: "contribution/basic-subtitle-player"
uid-meta: "contribution/basic-subtitle-player-meta"
comments: 
 items: 
  - uid: "69118"
  - uid: "69225"
uid-files: "contribution/basic-subtitle-player-files"
title: "Basic Subtitle Player"
contribution: "true"
---

This is a very basic patch, and surely there is more to do and better.

This reader is a stand alone patch with a GUI and a renderer.
It is dedicated to make subtitles on theatre or opera pieces. If you are in a hurry, well sure this may help.

Its very basic:
a text file contains the subtitles. 
They are formatted in a certain way, to get number of lines and separate the different subtitles:


```
##STR 1 2
This is my first row of text
This is my second row, wich will be readen

##STR 2 1
Because second argument is number of rows

##STR 3 4
In fact you have in 
this patch up to
4 different lines
wich will be printed
```

