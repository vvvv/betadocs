---
uid: "contribution/barcode1d-(texture)-spreadable-nodes"
uid-meta: "contribution/barcode1d-(texture)-spreadable-nodes-meta"
comments: 
 items: 
  - uid: "257674"
  - uid: "258248"
uid-files: "contribution/barcode1d-(texture)-spreadable-nodes-files"
title: "Barcode1d (Texture) spreadable nodes"
image: "Screenshot.jpeg"
contribution: "true"
---

The nodes are basic wrappers for the ZXing.Net library.  

There are two nodes to generate fully spreadable barcodes, qr-codes and various other types of codes based on a string of data. One outputs the generated code as EX9 the other one as DX11 textures.

A third nodes tries to read barcodes from provided DX11 Textures.

The nodes support 16 different formats and work on both 32 and 64 bit systems. Options for displaying text, font, font size and general width and height are provided.

Check <span class="pin">Status</span> for additional information regarding special format rules for specific types of codes.


###  Notes
The following formats do not currently have an implemented encoder:

* RSS (14 and Extended)
* MaxiCode
* All1d
* UPC EAN Extension
* IMB


###  Source
Source code for [v 1.0](https://github.com/ravazquez/barcode1d). 
Source code for [v 2.0](https://github.com/bj-rn/barcode1d). 

Feel free to add issues or expand the node as you see fit.

###  Installation
Download zip file and extract in your project. 



###  Changelog
#### v 2.0
* Width and Height pins replaced by Size(XY)
* New input for specifying the font
* New Nodes 
** Barcode1d (DX11.Texture) generating DX11 textures
** BarcodeReader (DX11.Texture String) reading barcodes from DX11 textures 
