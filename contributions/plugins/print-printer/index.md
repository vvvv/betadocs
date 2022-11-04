---
uid: "contribution/print-printer"
uid-meta: "contribution/print-printer-meta"
comments: 
 items: 
  - uid: "90046"
  - uid: "90047"
  - uid: "90049"
  - uid: "90052"
  - uid: "90061"
  - uid: "90099"
  - uid: "90202"
  - uid: "90250"
  - uid: "102976"
  - uid: "103016"
  - uid: "103267"
  - uid: "190895"
  - uid: "191011"
  - uid: "210591"
  - uid: "210683"
  - uid: "210720"
  - uid: "210896"
  - uid: "230297"
  - uid: "230348"
uid-files: "contribution/print-printer-files"
title: "Print & Printer"
image: "print_icon.jpg"
contribution: "true"
---

####  Print node
prints a texture

* Set printer by printer name pin
* x,y placement
* portrait/landscape
* set Color/grayscale
* Select Paper Size
* Scale to page (fit)
* Set print margins
* Using separate thread, does not block vvvv (via Tasks)
* Help patch
* Full source code

Not spreadable (yet)

####  Printer node
returns information about specific printer or all available printers,
if Printer Name is not supplied
Retrieves the following information about a printer:

* Printer Name
* If it is valid (online/offline)
* Duplex mode available
* Is it the default printer
* Does it support color print
* Information about supported paper sizes (Name, Code, Dimensions)
* Help patch
* Non blocking 
* Full source code

Takes some time to load all the info for each printer

<div class="box">
Note: The plugins are using c# .net 4.0 Tasks magic to implement non-blocking behavior, *please test and report if it works for you*. I have no idea, why it does - but it works for me :>

</div>