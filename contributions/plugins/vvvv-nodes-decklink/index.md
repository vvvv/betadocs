---
uid: "contribution/vvvv.nodes.decklink"
uid-meta: "contribution/vvvv.nodes.decklink-meta"
comments: 
 items: 
  - uid: "85275"
  - uid: "85279"
  - uid: "85282"
  - uid: "85288"
  - uid: "85289"
  - uid: "85338"
  - uid: "85379"
  - uid: "85380"
  - uid: "85382"
  - uid: "85383"
  - uid: "85388"
  - uid: "85400"
  - uid: "85403"
  - uid: "85404"
  - uid: "85405"
  - uid: "85407"
  - uid: "85409"
  - uid: "85411"
  - uid: "85425"
  - uid: "85455"
  - uid: "85513"
  - uid: "85520"
  - uid: "85838"
  - uid: "85851"
  - uid: "86043"
  - uid: "86162"
  - uid: "88798"
  - uid: "89456"
  - uid: "89466"
  - uid: "89475"
  - uid: "90221"
  - uid: "90223"
  - uid: "90224"
  - uid: "90251"
  - uid: "90266"
  - uid: "90694"
  - uid: "91380"
  - uid: "91381"
  - uid: "91390"
  - uid: "91432"
  - uid: "91860"
  - uid: "91928"
  - uid: "92065"
  - uid: "92311"
  - uid: "92320"
  - uid: "94935"
  - uid: "96890"
  - uid: "96908"
  - uid: "97357"
  - uid: "97378"
  - uid: "98296"
  - uid: "98373"
  - uid: "98432"
  - uid: "99167"
  - uid: "101866"
  - uid: "103403"
  - uid: "104398"
  - uid: "104494"
  - uid: "105855"
  - uid: "105883"
  - uid: "107881"
  - uid: "108720"
  - uid: "108728"
  - uid: "108729"
  - uid: "108810"
  - uid: "110593"
  - uid: "110649"
  - uid: "110873"
  - uid: "110907"
  - uid: "110908"
  - uid: "110909"
  - uid: "111270"
  - uid: "152932"
  - uid: "153167"
  - uid: "156499"
  - uid: "156755"
  - uid: "156762"
  - uid: "156764"
  - uid: "171176"
  - uid: "171461"
  - uid: "219865"
  - uid: "219942"
uid-files: "contribution/vvvv.nodes.decklink-files"
title: "VVVV.Nodes.DeckLink"
image: "VideoIn (DeckLink EX9.Texture) help.png"
contribution: "true"
---

1.  Introduction
BlackMagic Design produce some pretty interesting products in the video market. Of particular interest to VVVV users is the Intensity range of products <http://www.blackmagic-design.com/products/intensity/> which allows a computer to capture video live from another video source (e.g. a laptop, a video camera) over a range of video connectors (HDMI, composite, component), and the Intensity product is available in a number of packages (USB3.0, PCIe, thunderbolt). They start at $200.

An example usage scenario would be to generate visuals on computer A (e.g. this could be a Mac running Modul8), output them on DVI and connect this to the HDMI input of the BlackMagic Intensity, and then capture that content into VVVV as a texture.

Traditionally this has been possible using DirectShow, but this route has always caused noticeable latency (which increases over time). Using this plugin introduces near-zero latency (as fast as the card will allow).

1.  Latency
[bjeorn](http://vvvv.org/users/bjeorn) below states 2-3 frames latency between PC A's monitor when capturing and presenting on PC B's monitor by videoing a counter on both screens.


1.  Usage
Use the ListDevices (DeckLink) node to give you IDeckLink devices, which you then can plug into the VideoIn (DeckLink EX9.Texture) node. Make sure to select the correct video mode on the VideoIn node to correspond with the signal being sent to the capture device (this is not automatic).

Note that the texture output from the plugin is in a strange YUV format, and to decode it, you will need to use the YUV2RGB TextureFX (supplied in this package).

If your computer is very slow (or very busy), then it may not be able to keep up with the capture device, in which case it will begin to buffer frames to make sure that you don't miss anything. In this case, if you do want to improve the latency of the stream, then bang the Flush input of VideoIn to flush the cache (feel free to attach a toggle to flush every frame).

1.  Notes on YUV2RGB
##  Why YUVtoRGB?
I found the data which comes out from the BlackMagic Intensity to be in YUV format (UYVY). On my system (ATI 6770, Intel Core i7 * 4/4), I couldn't get any of the native DirectX YUV texture formats to work. Furthermore, I found decoding the data on the CPU to be a serious issue in C# as it doesn't allow for native 8-bit math (it casts to 32-bit integers whenever you perform an operation which may result in overflow). There are 2 formats offered by SlimDX (YUY2 and Uyvy) which would be ideal, but trying to create one of these textures threw an error on my system (often these texture types can be GPU specific). In the end, the cleanest/quickest solution seemed to be to ship the data to the GPU and decode it there.

##  What does YUVtoRGB do?
So YUV is a colour encoding which reformats the RGB information in order of visual importance:
1. Y = lightness
1. U = distance from blue
1. V = distance from red

Often we transmit images with full resolution Y, but compressed resolution U and V, which is the case for the BlackMagic Intensity driver. A 4:2:2 pulldown takes every 2 pixels (RGBRGB=6 bytes) and stores it as (UYVY=4 bytes).

This means that 2 pixels are stored in 4 bytes. Since 4 bytes can be stored in a single RGBA pixel, this is what I did coming out of the VideoIn node. This is then decoded in a shader back into RGB.

Since each 'fake RGBA' pixel coming out of VideoIn is turned into 2 real RGB  pixels, the resolution coming out of VideoIn is actually half the width of the final image.

1.  Troubleshooting
As always, plugins might show some bugs when released in the wild. 
The first thing to do is check that your capture is working correctly in BlackMagic Media Express application. If you can see a live image in that application when in 'Log and Capture' mode (and having the right format set in Preferences) but you can't get it working in VVVV, then please comment below to help debug. If you can't get it working in Media Express, then please look into that first.

1.  Changelog
##  v1.1
###  Features
* Added 'Wait For Frame' options. See help patch for details]
* Added 'Frame Received' output message
###  Bug fixes
* Fixed exception that sometimes occurred when changing video format.
