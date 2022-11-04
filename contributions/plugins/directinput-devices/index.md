---
uid: "contribution/directinput-(devices)"
uid-meta: "contribution/directinput-(devices)-meta"
uid-files: "contribution/directinput-(devices)-files"
title: "DirectInput (Devices)"
contribution: "true"
---

simple stuff. outputs relative mouse data in mickies, and outputs all the buttons (including MB4 and MB5) also outputs direct data about keyboard.
based on: <http://msdn.microsoft.com/en-us/library/windows/desktop/bb153252(v=VS.85).aspx>

i've created this because <span class="node">Mouse (System Global)</span> and <span class="node">Keyboard (System Global)</span> was buggy for me in certain situations (they don't work in multiple instances of vvvv, and sometimes cycle mode is buggy)

also i attached a <span class="node">Camera (Transform Softimage)</span> mod using this plugin for a better example.

Read the help patch! it contains several warnings!