---
uid: "contribution/stringreplacer-plugin-(useful-with-fantastick-plugin)"
uid-meta: "contribution/stringreplacer-plugin-(useful-with-fantastick-plugin)-meta"
comments: 
 items: 
  - uid: "64310"
  - uid: "64315"
  - uid: "64431"
  - uid: "64447"
  - uid: "64456"
  - uid: "64476"
  - uid: "64480"
  - uid: "64495"
  - uid: "89379"
uid-files: "contribution/stringreplacer-plugin-(useful-with-fantastick-plugin)-files"
title: "StringReplacer Plugin (useful with Fantastick Plugin)"
contribution: "true"
---

This plugin is a generic string replacement sort-of thing. 

StringReplacer.zip: Includes 3 dynamic plugins for doing string replacements. The most useful of these 3 plugins is StringReplacerSpreadable. These plugins are very useful for injecting information from your vvvv patch into your Fantastick JS code.

For Example:

Input:
Hello, my name is $1, I am feeling very $2, how about you, $3, are you $2?

Replacements:
$1 = John, $2 = happy, $3 = Bill

Output:
Hello, my name is John, I am feeling very happy, how about you, Bill, are you happy?