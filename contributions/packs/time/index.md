---
uid: "contribution/time"
uid-meta: "contribution/time-meta"
comments: 
 items: 
  - uid: "111681"
  - uid: "111685"
  - uid: "111768"
  - uid: "111891"
  - uid: "114197"
  - uid: "152520"
  - uid: "152528"
  - uid: "152549"
  - uid: "152557"
  - uid: "153938"
  - uid: "154037"
  - uid: "154913"
  - uid: "154917"
  - uid: "155304"
  - uid: "155397"
uid-files: "contribution/time-files"
title: "Time"
image: "worldclock.png"
contribution: "true"
---

If you also think that using the Astronomy nodes to handle times and dates is a pain then this pack could make you happy.

1.  Version history
**Since v0.5.6**
* small bugfix in select nodes

**Since v0.5.5**
* vvvv beta33.3 compatibility
* added JSON serializing (important if you use time in your own plugin and want to de/serialize the object in JSON format)

**Since v0.5.4**
* vvvv beta33 compatibility
* fixed toString method in core dll (important if you use the nuget package VVVV.Packs.Time)

**Since v0.5**
* vvvv beta32 compatibility
* Fixed a bug in AsTime (Value Decimal)

**Since v0.4**
* AsTime (Value Decimal Advanced)
* AsTime (Value Decimal)
* AsTime (Value Unix)
* S+H (Time Timespan)

* Fix: currentTime is synced to vvvv-internal frames now (as suggested here: https://github.com/letmp/vvvv-Time/issues/4 )

**Since v0.3 (thanks to sebl):**
* AsValue (Time Decimal)
* AsValue (Time Unix)
* AsString (Time Unix)

**Since v0.1**
* CurrentTime (Time)
* LocalTimezone (Time)
* ChangeTimezone (Time)
* AsTime (String)
* AsTime (Value)
* AsString (Time)
* AsString (TimeSpan)
* Time(Time Split)
* Time(Time Join)
* Zip (Time)
* Unzip (Time)
* Sort (Time)
* + (Time, TimeSpan)
* - (Time, TimeSpan)
* - (Time, Time)
* + (TimeSpan, TimeSpan)
* - (TimeSpan, TimeSpan)
* TimeSpan (Time Join)
* TimeSpan (Time Split)
* Select (Time)
* Select (Time Bin)
* > (Time)
* < (Time)
* = (Time)
* S+H (Time)
* GetSlice (Time)
* SetSlice (Time)
* DeleteSlice (Time)

1.  Install Guide
* Download relevant version
* Copy folder into vvvv directory, like you would do for addonpack

1.  Source Code
You can find the source code here:
<https://github.com/letmp/vvvv-Time>

1.  Nuget
You can use vvvv-time in your own project by adding VVVV.Packs.Time as nuget dependency to make your nodes compatible with this contribution.
<https://www.nuget.org/packages/VVVV.Packs.Time/>

Comments and bugreports are highly appreciated!