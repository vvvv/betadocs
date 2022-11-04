---
uid: "contribution/obsolete-see-addonpack-json-aselement"
uid-meta: "contribution/obsolete-see-addonpack-json-aselement-meta"
comments: 
 items: 
  - uid: "96870"
  - uid: "98269"
  - uid: "98272"
  - uid: "98564"
  - uid: "100129"
  - uid: "102283"
uid-files: "contribution/obsolete-see-addonpack-json-aselement-files"
title: "[OBSOLETE, see Addonpack] JSON AsElement"
contribution: "true"
---

**Note: is in addonpack since vvvv45beta30.**

Converts a JSON string to XElement for use with all the nice XElement nodes. And is spreadable.

Uses the standard .NET parser for JSON files. See <https://mutelight.org/using-the-little-known-built-in-net-json-parser> for implementation info (I did a nearly 1:1 copy of that).

Oh, and when "success" pin is false, you can see what went wrong in the TTY Renderer.