---
uid: 373b8cb9-a6d5-4d6d-837e-0062fd2673f3
---

# SpanMode vs. DualView
On Windows XP graphic card drivers offer two different modes to use multiple monitors on 1 card:  
* SpanMode treats multiple monitors together as one DirectX device.   
* DualView treats each monitor as a single DirectX device.  

A current limitation of <span class="node">Videotexture (EX9.Texture)</span> and <span class="node">VideoTexture (EX9.Texture YUVMixing)</span> is that they can only playback on one DirectX device at a time. Meaning that in DualView you can see them only on one monitor.  

## SpanMode (only available on Windows XP)
* Multiple monitors together form one DirectX device  
* Renderers always go fullscreen spanning over all the outputs of the graphic card  
In this mode you can play videotextures on multiple monitors, but you can't go fullscreen on only one of the monitors and have the patches on the other. SpanMode always only works on one graphiccard, the desktop cannot be spanned via several graphiccards.  

## DualView
* A DirectX device is created for each ouptut on the graphic card  
* Renderers go fullscreen on individual outputs independently  
In this mode a videotexture plays only on one of the outputs at a time and you can go fullscreen with a renderer on one monitor while still patching on the other.   

## Mosaic Mode in Windows 7 with Nvida Graphic Cards

You can use Span Mode in Windows 7 by simply going in the Nvida Control Pannel and setting it up. There it is called Mosaic-Mode.  

You can also download configureMosaic.exe from the Nvdia page and use the following commandline parameters to activate it:  

    > cd c:\Path\
    > configureMosaic.exe set rows=1 cols=3 overlap=0,0 res=1920,1080,60

This might be handy if you want vvvv or a startup script to set up the span mode.  

## Overcomming the VideoTexture limitations
### Option 1
Use two filestreams and two videotextures where each is connected to one of the renderers to see video on both renderers/devices but they'll probably not be in sync and you risk bad performance.  

### Option 2
Use VideoIn/FileStream->sharedmem->videotexture->quad  
for one device. and then use sharedmemtexture->quad for the other devices.   
> ggml:  
21.11.08 23:19:
videoin across shared memory works streched on 3 videocards pretty well. if anyone interested, i can report precise performance and system information.  
  

## Expanding Windows' SpanMode
* **Graphics expansion modules** are small black boxes that let you connect two or three monitors to a single VGA, DVI or DisplayPort output and use your system's GPU across all monitors. Via a custom <a href="http://en.wikipedia.org/wiki/EDID" class="extURL" target="_blank">EDID</a> they make your PC believe that only one monitor with a  resolution of e.g. 3072*768 Pixel is connected. Well known products are <a href="http://www.matrox.com/graphics/en/products/gxm/dh2go/" class="extURL" target="_blank">Matrox DualHead2Go</a> and <a href="http://www.matrox.com/graphics/en/products/gxm/th2go/" class="extURL" target="_blank">Matrox TripleHead2Go</a>  
* **AMD EyeFinity Technology** a.k.a. <a href="http://en.wikipedia.org/wiki/Evergreen_%28GPU_family%29" class="extURL" target="_blank">Evergreen</a> supports multiple display outputs simultaneously as one large SpanMode. Used in ASUS' graphic card line 'Radeon' EyeFinity enables massive desktop workspaces, e.g. you can connect 6 monitors with each FullHD resolution to the graphic card and then go fullscreen with only one DirectX renderer.  


# Links
## related vvvviki-pages
* [Device (EX9 Auto)](https://vvvv.org/documentation/device-(ex9-auto))
* [Device (EX9 Manual)](https://vvvv.org/documentation/device-(ex9-manual))

## related vvvvorum-threads
* <a href="https://discourse.vvvv.org/t/best-method-to-span-renderer-across-multiple-screens/16412" class="extURL" target="_blank">Best method to span renderer across multiple screens</a>  
* <a href="https://discourse.vvvv.org/t/spanmode-related-questions" class="extURL forum" target="_blank">spanmode-related-questions</a>  
* <a href="https://discourse.vvvv.org/t/Multi screen recommendations" class="extURL forum" target="_blank">Multi screen recommendations</a>  
* <a href="https://discourse.vvvv.org/t/newbie dual renderer window question" class="extURL forum" target="_blank">newbie dual renderer window question</a>  
* <a href="https://discourse.vvvv.org/t/framerate chrashes when dragging the 2nd renderer on the 2nd screen" class="extURL forum" target="_blank">framerate chrashes when dragging the 2nd renderer on the 2nd screen</a>  
* <a href="https://discourse.vvvv.org/t/videoin across multiscreen" class="extURL forum" target="_blank">videoin across multiscreen</a>  
* <a href="https://discourse.vvvv.org/t/startup in multiple fullscreens" class="extURL forum" target="_blank">startup in multiple fullscreens</a>  
* <a href="https://discourse.vvvv.org/t/DX Performance" class="extURL forum" target="_blank">DX Performance</a>  
* <a href="https://discourse.vvvv.org/t/Lots of questions..." class="extURL forum" target="_blank">Lots of questions...</a>  
* <a href="https://discourse.vvvv.org/t/NVPerfHUD in Fullscreen" class="extURL forum" target="_blank">NVPerfHUD in Fullscreen</a>  
* <a href="https://discourse.vvvv.org/t/VIsta dualview two cards 4 screens" class="extURL forum" target="_blank">VIsta dualview two cards 4 screens</a>  