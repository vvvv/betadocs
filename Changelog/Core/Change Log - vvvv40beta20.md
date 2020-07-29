---
uid: 28e19aab-fd98-4866-bf6d-ca71cee4456f
---

# Change Log - vvvv40beta20
released on 24 12 08  

## general
* save gets more insisting, secure and expressive in its error messages.  
* copy & paste uses windows clipboard. you also can paste the xml snippets into a text editor.  

## fixed nodes
* Renderer (HTML URL) now sits in its window properly and can render onto GDITexture even if hidden by another window/fullscreen  
* Renderer (HTML String) can now render onto GDITexture even if hidden by another window/fullscreen  
* OSCEncoder (Network): had a memoryleak when not sending as bundle and may have returned wrong status.  
* Kalle (VVVV) is now a proper singleton.  

## improved nodes
* GDITexture (EX9.Texture) can now render with alpha channel, if texture format with alpha channel is selected (mostly useful for rendering of Text (GDI)). got an additional pin "Enabled" which allows to disable rendering independent of the connected renderer  
* DX9Texture (EX9.Texture) can now render with antialiasing (but not when using multiple rendertargets)  
* Decay (Animation) now can attack into two directions and decay back to one value, the turning point. use Terrain-pin and select "Valley".  
* HSL (Transform), added input pin to set a factor for the alpha channel  

## new nodes
* Clipboard (Windows String Get) outputs the current clipboard-content <a href="http://vvvv.org/tiki-view_forum_thread.php?comments_parentId=23575&topics_threshold=0&topics_offset=12&topics_sort_mode=lastPost_desc&topics_find=&forumId=7" class="extURL" target="_blank">see</a>  
* Clipboard (Windows String Set) copies a given string to the clipboard   
* Lumax (Devices) - untested  
* QuickNodes (VVVV) ?  

## new shader
* Bicubic.fx, high quality texture scaling  
* most shaders have an alpha pin for easy fading now