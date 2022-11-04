---
uid: "contribution/global-s-r-nodes"
uid-meta: "contribution/global-s-r-nodes-meta"
comments: 
 items: 
  - uid: "264329"
  - uid: "264330"
  - uid: "264394"
  - uid: "264395"
  - uid: "264396"
  - uid: "264397"
  - uid: "265467"
  - uid: "265522"
  - uid: "265709"
  - uid: "268632"
  - uid: "268652"
  - uid: "268662"
  - uid: "268743"
  - uid: "268755"
  - uid: "268756"
uid-files: "contribution/global-s-r-nodes-files"
title: "Global S & R nodes"
image: "Global_Teacher_Prize_Top_50_855_513_48.jpg"
contribution: "true"
---

This is a global S & R set of nodes which will allow users to send values from multiple locations in their application into a centralized "global variable" and receive all values in the same frame as a spread anywhere else on their application.

Useful for example to store lists of values such as application-wide used fonts, configuration parameters, etc.

For a working example check out \vvvv\girlpower inside the download zip.

Cheers!

###  Features
* Nodes come with support for Value, String, Color, Raw and Transform data types
* Input spreads for all data types are supported
* <span class="pin">Clear</span> pin allows resetting of the full value spread from any S or R node with the same <span class="pin">Name</span>
* <span class="pin">Avoid Duplicates</span> pin prevents existing values from being sent
* <span class="pin">Add</span> pin allow you to control when the data is sent

The nodes work on both 32 and 64 bit systems.

### Source 
Source code is available via github here:<https://github.com/ravazquez/globalSR>.

Feel free to add issues or expand the nodes as you see fit.

### Installation
Download zip file and extract in your project.

To use in your own patches just drag and drop \lib\GlobalSR.dll into your patch and select the version you need (String, Value, Color, etc.)

