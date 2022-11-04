---
uid: "contribution/vvvv-message"
uid-meta: "contribution/vvvv-message-meta"
comments: 
 items: 
  - uid: "97791"
  - uid: "97813"
  - uid: "97842"
  - uid: "97924"
  - uid: "97937"
  - uid: "97941"
  - uid: "98018"
  - uid: "98066"
  - uid: "102561"
  - uid: "103166"
  - uid: "103169"
  - uid: "103174"
  - uid: "103178"
  - uid: "103385"
  - uid: "103401"
  - uid: "103511"
  - uid: "103541"
  - uid: "104340"
  - uid: "111048"
  - uid: "111052"
  - uid: "111058"
  - uid: "155429"
  - uid: "155431"
  - uid: "155434"
  - uid: "155440"
  - uid: "155458"
  - uid: "155470"
  - uid: "155476"
  - uid: "155520"
  - uid: "155731"
  - uid: "155733"
  - uid: "155734"
  - uid: "156447"
  - uid: "156494"
  - uid: "159652"
  - uid: "159661"
  - uid: "169535"
  - uid: "169537"
  - uid: "177925"
  - uid: "182008"
  - uid: "182014"
  - uid: "182079"
  - uid: "185585"
  - uid: "187841"
  - uid: "187844"
  - uid: "188183"
  - uid: "191121"
  - uid: "196437"
  - uid: "196460"
  - uid: "206947"
  - uid: "206978"
  - uid: "207068"
  - uid: "232434"
  - uid: "232442"
  - uid: "232473"
  - uid: "232488"
  - uid: "233581"
  - uid: "233583"
  - uid: "233591"
  - uid: "236454"
  - uid: "236455"
  - uid: "239147"
  - uid: "239208"
  - uid: "241313"
  - uid: "242051"
  - uid: "242806"
  - uid: "242821"
  - uid: "242822"
  - uid: "242835"
  - uid: "246934"
uid-files: "contribution/vvvv-message-files"
title: "vvvv-Message"
image: "icon_11.png"
contribution: "true"
---

The vvvv-Message pack has been in open development for four years. In that time it grew alongside free and commercial projects involving the likes such as Projection Mappings, Device Bindings, UI Widget Handling, On-Site Data Plumbing, Web Parsing, Boygroup Replacement, and not least, Bus Driven Patch Architecture.

The pack is exposing the [SharpMessage](https://www.nuget.org/packages/SharpMessage/) functionality to vvvv in a fully spreadable way.

####  Install
<div class="box">
You can use this [VPM](vpms://raw.githubusercontent.com/velcrome/vvvv-Message/master/copy/vvvv-Message.vpack) link to directly install the latest fully supported version with all dependencies  

Alternatively, the latest releases and prereleases will always be at the [GitHub Release](https://github.com/velcrome/vvvv-Message/releases) page, just create a directory *packs/vvvv-Message* and unpack to there.</div>

####  Getting Started
Use F1. Look at the help patches, if you are in doubt, because there is a lot of information in them. The shortest route to try out Message, however, is the 101 girlpower.

Anyway, first two nodes advised to check out are **ConfigKeep** and **Split**. 

If you feel comfortable with splitting and maybe even editing, understand that a Message can become stateful (i.e. across time, not just a single vvvv frame) when kept inside a Keep.

<div class="box">
Note:
It helps if you can make yourself unlearn AvoidNil, Framedelay, S+H, Change and their family. There should always be a solution without duplicating some of them; the Message nodes can be smart enough themselves. If you still "need" them in bulk, chances are you haven't found the best combination of Defaults and Keeps yet. Oh, and abolish S and its evil twin R, that helps too.
</div>

####  Mission
The original idea of this pack sounds convoluted: make plugins with easily typeable io pins and use that to retain order in bigger patches and saving lots and lots of links by simply *packing* all kinds of attributes in a single meaningful object and handling that object in a very easy and data flowing manner. But it is plain: teach vvvv how to write layouted letters and fill them into marked envelopes, meant to be given from hand to hand.

Goes without saying, but every hand in this metaphor is a of course a [node](https://github.com/velcrome/vvvv-Message/tree/master/src/MessageNodes). And there are no letters or envelopes of any paper or other material kind, but only smart C# **Messages**, trademarked with a proper Topic and automatic localized timestamping. 

Use nodes to create, read and write, reshape, analyze, search and sift Messages, and, probably most useful, [keep](https://github.com/velcrome/vvvv-Message/blob/master/src/MessageNodes/doc/Keep.md) them and use them as stateful objects that can be manipulated anywhere else in your patches' folds. 

Message is meant to be open, it strives to connect with other relevant protocols.

####  Features
42 vvvv nodes total: Don't let the number fool you, most of the time you will not need more than a dozen of them, but this is a vetted pro pack. So you get the full suite to freely evaluate and even use it in non-commercial work, as seems fair.

* At first glance, it might sound the most boring of all, that you can tightly define the structures of your Messages, both per-node (thankfully in a custom vvvv window) and for many nodes simultaneously across entire applications. This [feature](https://github.com/velcrome/vvvv-Message/blob/master/src/MessageNodes/doc/Formular.md) is called **Form**ular (yay, more Kafka to the vvvv)! 

<div class="box">
Note:
Once at this meta level of patching, you don't have to replicate structure for your data anymore, but simply select your predefined Formular and get the benefits of named and typed pins - anywhere in your patch. 
</div>
* Industry standard serialisation with both [Json.NET](http://james.newtonking.com/projects/json-net.aspx) and binary [MsgPack](http://msgpack.org/index.html) are available to help with persisting, streaming or even distributing data among vvvv instances - local and networked. Additionally it helps to establish api bindings with good ole' OSC. 

* It comes with girlpower examples showing how to connect to TouchOSC, Ableton, Reaktor, XTouch midi interface and Duration, just to showcase its broad versatility and making all these things easily accessible through **Message** manipulation.

* For reliable ethernet comm with **Message** check out [ZeroMQ](xref:contribution/vvvv-zeromq).

* Extending traditional data-flow, the pack allows down-stream edits (i.e. **Message** is conciously mutable). This is big, because it helps any project, where you need read-write access to your data across patches without having to resort to framedelays. The pack's change management is just the icing to the fact.

Oh, you can also put DX11 resources into a Message. Or a spread of Messages in a Message. However deep you'd like to go. But that is totally up to you. 

####  License
This is released with Creative Commons BY-NC-SA 4.0, so no commercial use!

If you need a license other than that contact us at license@intolight.de
Consider that intolight rates start at €42 per vvvv license, and compare that to the productivity you gained. 