---
uid: "contribution/map-(advanced)"
uid-meta: "contribution/map-(advanced)-meta"
comments: 
 items: 
  - uid: "110916"
  - uid: "110939"
  - uid: "111044"
  - uid: "111053"
uid-files: "contribution/map-(advanced)-files"
title: "Map (Advanced)"
image: "nikolaus.gif"
contribution: "true"
---

Ho Ho Ho,

here it is again, the season of givvvving and merry sharing. 

Since today is the [Saint Nicholas Day](http://en.wikipedia.org/wiki/Saint_Nicholas_Day) I want to offer my new plugins for download that are an alternative to <span class="node">Map (Value)</span> and <span class="node">MapRange (Value)</span>. They are quite optimized, so with spreadcounts higher than a few hundreds it really starts to make a performance difference. Good improvement :)

At its core it fixes the old problem, that the <span class="pin">Mapping</span> was never spreadable {1}. 
Additionally I added a hidden, but fully usable <span class="pin">BinSize</span>, next to the <span class="pin">Input (Value)</span>. With the binsize you can define how many <span class="pin">Input (Value)</span> slices are used for each of the other 4+1 pins that follow to the right. 

<div class="box">
* MapFast.zip version is completely different code, with correct spreading and bin size behaviour. even faster at lower slicecounts, a bit slower at higher ones (though still faster than native)</div>

<div class="box">
* this is not spreading as best practice advises, but then again, with <span class="node">Map (Value)</span> and <span class="node">MapRange (Value)</span> you usually just want the <span class="pin">Input (Value)</span> calced to <span class="pin">Output (Value)</span> anyway. So SpreadMax is fixed to that, superfluos (and potentially flawed) slice sets for the mapping are ignored. Till then they spread beautifully.</div>

<div class="box">
* {1} I didn't fix the problem of having a **Map**ping Enum Pin on a **Map** node, for backward compatibility reasons. Monsters, ehh</div>
1.  XMAS
I know this is kind of strange stuff seemingly unrelated to christmas, but I am sure a lot of you have little secret boxes in their workflows somebody else could use or learn from. 

Don't be shy to spam contributions. 
You can be sure, somebody else just tries to reinvent the wheel you discovered half a year ago. 

Sure, we all have a lot to do, especially at the end of the year. But remember: an hour of your time for completing and sharing a patch, a plugin, a pack, a module, or (not the least!) a helppatch can save days for a whole bunch of people struggling with the same learing curve, just as you did. Don't be shy