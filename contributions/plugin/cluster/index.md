---
uid: "contribution/cluster"
uid-meta: "contribution/cluster-meta"
comments: 
 items: 
  - uid: "58629"
  - uid: "58755"
  - uid: "58769"
  - uid: "58813"
  - uid: "58815"
  - uid: "80619"
  - uid: "80620"
  - uid: "85284"
  - uid: "85286"
uid-files: "contribution/cluster-files"
title: "Cluster"
contribution: "true"
---

Cluster is a simple algorithm for merging Pointclouds. May be useful for simplifying contourdata. sometimes it will be reasonable to use two Clusters in row..

**ONLY >=v25**

- v0.8 - simple Algorithm coded

All hints and experiences are greatly appreciated.
discussionthread - <http://vvvv.org/forum/following-tracked-objects-(n%3E1)>

**v1.0 Changelog**

based on dbscan, now it works far more robust against noise. changed category from value to 2d. some extras like lifecycle, motionvectors & automatic linear movement after losing tracking, affinity of the points (0=noise, 1=empty, then the clusters) and so on, try it and leave your messages, ideas & hints here or in the thread linked above.
