---
uid: "contribution/vvvv.datatable"
uid-meta: "contribution/vvvv.datatable-meta"
comments: 
 items: 
  - uid: "175849"
  - uid: "175850"
  - uid: "175851"
  - uid: "175866"
  - uid: "185524"
  - uid: "185529"
  - uid: "185531"
  - uid: "185533"
  - uid: "185534"
  - uid: "185535"
  - uid: "185536"
  - uid: "185584"
  - uid: "190190"
  - uid: "190197"
  - uid: "190222"
  - uid: "190277"
  - uid: "190282"
  - uid: "190285"
  - uid: "190286"
  - uid: "190438"
  - uid: "190485"
  - uid: "199896"
  - uid: "199897"
  - uid: "199898"
  - uid: "209936"
  - uid: "210204"
  - uid: "222856"
uid-files: "contribution/vvvv.datatable-files"
title: "VVVV.DataTable"
image: "DataTable (Demo)-MyTable_2014.11.24-16.47.10.png"
contribution: "true"
---

Persistent data handling with GUI.

Supports type boolean, int, float/double and string.

Heavily based on VVVV.Nodes.TableBuffer by [elliotwoods](http://vvvv.org/users/elliotwoods)

Mixed type support and GUI convenience sponsored by [m-box](http://www.m-box.de/).

v1.2:
* set nodes set pin changed from bang to toggle
* insert nodes insert pin changed from bang to toggle
(bang type was preventing alteration in subsequent frames)

v1.1:
* fixed wrong output slicecount on GetRow Dynamic
* culture info is set to invariant culture
* copy paste handles arbitrary decimal separator

Source Code:

<https://github.com/woeishi/VVVV.DataTable>