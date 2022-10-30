---
uid: "contribution/metaio"
uid-meta: "contribution/metaio-meta"
comments: 
 items: 
  - uid: "186741"
  - uid: "186744"
  - uid: "186745"
  - uid: "186831"
  - uid: "186876"
  - uid: "188283"
  - uid: "191080"
  - uid: "191081"
  - uid: "192166"
  - uid: "192187"
  - uid: "197448"
  - uid: "197454"
  - uid: "197621"
  - uid: "197675"
  - uid: "197742"
  - uid: "198519"
  - uid: "198571"
  - uid: "198699"
  - uid: "198716"
  - uid: "198822"
  - uid: "198861"
  - uid: "199410"
  - uid: "199767"
  - uid: "199792"
  - uid: "211775"
  - uid: "211945"
  - uid: "212144"
  - uid: "213090"
  - uid: "213149"
  - uid: "216288"
  - uid: "219983"
  - uid: "220128"
  - uid: "220593"
  - uid: "221092"
  - uid: "221206"
  - uid: "221500"
  - uid: "222367"
  - uid: "229351"
  - uid: "247572"
  - uid: "254986"
uid-files: "contribution/metaio-files"
title: "metaio"
image: "metaio.png"
contribution: "true"
---

plugin for high-quality AR solution using Metaio SDK.

<div class="box">
Note:
metaio stopped all services at May 2015, because of apple acquired metaio. you cannot download sdk from web site no more and their web site will be closed soon.
if you already installed sdk, this plugin works fine but you cannot use this for any public projects.
</div>

### Features
high speed and stable tracking by various way.
* ID Marker Tracking
* Picture Marker Tracking
* Image Tracking
* Instant(snapshot) Tracking
* 3D SLAM Tracking
* CAD based 3D Tracking
* Face Tracking

### Installation
1. download & install latest Metaio SDK from [here](http://ar.metaio.com/download_sdk). (requires an account)
1. download this plugin and extract .zip file.
1. open Metaio SDK folder (ie: C:\metaio\Metaio SDK 6.0.2\_Windows\metaioSDK\vc100\x86_release\bin)
1. copy the three dll files to here.
1. run vvvv and open Root patch(Alt+R), then add Metaio SDK folder to vvvv path
1. open helppatch to check setup complete

---

### Change Log
**2015.4.24 (v1.1)**
* add Property Page pin to VideoIn node
* support CAD Model tracking with Metaio node
* 2D instant tracking works with InstantTracking node
* add Success out pin to InstantTracking node
* new node
** **AsSource**: use any texture as source for tracking. texture must be convert as raw data.

---

requires beta33.x, tested 32bit only.